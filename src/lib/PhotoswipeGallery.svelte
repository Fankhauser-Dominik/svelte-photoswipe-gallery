<script lang="ts">
import {
    onMount
} from "svelte";
import {
    tick
} from "svelte";

import PhotoSwipeLightbox from './Photoswipe/photoswipe-lightbox.esm.js';
import PhotoSwipeFullscreen from './Photoswipe/photoswipe-fullscreen.esm.js';
import './Photoswipe/photoswipe.css';
import './styles.css';
export let galleryID: string = "Svelte-Photoswipe-Gallery";
export let gap: number = 10;
export let maxColumnWidth: number = 250;
export let hover: boolean = false;
export let loading: string = "lazy";
export let images: any[] = [];
export let showDescription: boolean = true;
export let showDownloadButton: boolean = true;
export let showFullscreenButton: boolean = true;

let columns: any[] = [];
let galleryWidth: number = 0;
let columnCount: number = 0;

$: columnCount = parseInt(galleryWidth / maxColumnWidth) ?? 1;
$: columnCount && Draw();
$: galleryStyle =
    "grid-template-columns: repeat(" +
    columnCount +
    ", 1fr); --gap: " +
    gap +
    "px";
onMount(Draw);

async function Draw() {
    await tick();

    if (!images) {
        return;
    }

    columns = []
    // Fill the columns with image URLs
    for (let i = 0; i < images.length; i++) {
        const idx = i % columnCount;
        columns[idx] = [
            ...(columns[idx] || []),
            {
                src: images[i].src,
                preview: images[i].preview,
                description: images[i].description,
                width: images[i].width,
                height: images[i].height,
                alt: images[i].alt,
                class: images[i].className,
                index: i
            },
        ];
    }
}

let lightbox = new PhotoSwipeLightbox({
    gallery: '#' + galleryID,
    // children: 'a',
    pswpModule: () => import('$lib/Photoswipe/photoswipe.esm.js'),
    dataSource: images,
});

lightbox.on('uiRegister', function() {
    if (showDescription) {
        lightbox.pswp.ui.registerElement({
            name: 'custom-caption',
            order: 9,
            isButton: false,
            appendTo: 'root',
            html: 'Caption text',
            onInit: (el: any) => {
                lightbox.pswp.on('change', () => {
                    const currSlideElement = lightbox.pswp.currSlide.data;
                    let alt = '';
                    let description = '';
                    if (currSlideElement) {
                        alt = currSlideElement.alt;
                        description = currSlideElement.description;
                    }
                    el.innerHTML = description ?? alt ?? '';
                });
            }
        });
    }
});

if (showDownloadButton) {
    lightbox.on('uiRegister', function() {
        lightbox.pswp.ui.registerElement({
            name: 'download-button',
            order: 8,
            isButton: true,
            tagName: 'a',

            html: {
                isCustomSVG: true,
                inner: '<path d="M20.5 14.3 17.1 18V10h-2.2v7.9l-3.4-3.6L10 16l6 6.1 6-6.1ZM23 23H9v2h14Z" id="pswp__icn-download"/>',
                outlineID: 'pswp__icn-download'
            },

            onInit: (el: any, pswp: any) => {
                el.setAttribute('download', '');
                el.setAttribute('target', '_blank');
                el.setAttribute('rel', 'noopener');

                pswp.on('change', () => {
                    el.href = pswp.currSlide.data.src;
                });
            }
        });
    });
}

if (showFullscreenButton) {
    let fullscreenPlugin = new PhotoSwipeFullscreen(lightbox);
}

lightbox.on('close', function() {
    lightbox.init();
});

onMount(() => {
    lightbox.init();
    return () => {
        lightbox.destroy();
    };
});

const onClick = (index: number) => {
    lightbox.loadAndOpen(index);
}
</script>

<div id="gallery" bind:clientWidth={galleryWidth} style={galleryStyle}>
    {#each columns as column}
    <div class="column">
        {#each column as img, index}
        <img
            src={img.preview ?? img.src}
            alt={img.alt}
            class="{hover === true ? 'img-hover' : ''} {img.class} GalleryImage"
            {loading}
            on:click={() => onClick(img.index)}
        />
        {/each}
    </div>
    {/each}
</div>
