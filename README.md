# Svelete PhotoSwipe Gallery

The easiest way to us a Photoswipe Lightbox with a Masonry Gallery in Svelte.

## How to use it

```html
<script>
	import PhotoswipeGallery from 'svelte-photoswipe-gallery';

	const images = [
		{
			src: 'https://source.unsplash.com/random',
			preview: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet',
			alt: 'Random'
		}
	];
</script>

<PhotoswipeGallery
	{images}
	showDescription="{false}"
	showDownloadButton="{false}"
	showFullscreenButton="{false}"
/>
```

## Options

| Name                 | Type    | Default | Description                                                             |
| -------------------- | ------- | ------- | ----------------------------------------------------------------------- |
| images               | Array   | []      | Array of image objects with at least src, width and height              |
| showDescription      | Boolean | true    | Shows the description of the image at the bottom of the opened Lightbox |
| showDownloadButton   | Boolean | true    | Shows the download button in the opened Lightbox                        |
| showFullscreenButton | Boolean | true    | Shows the fullscreen button in the opened Lightbox                      |

## Image Object

| Name        | Type   | Required             | Description                                                                                                                                                                                   |
| ----------- | ------ | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| src         | String | yes                  | The source of the image.                                                                                                                                                                      |
| preview     | String | no                   | The source of the preview image, if given, that's the image shown in the Masonry Gallery.                                                                                                     |
| width       | Number | yes                  | The width of the image in the opened Lightbox.                                                                                                                                                |
| height      | Number | yes                  | The height of the image in the opened Lightbox.                                                                                                                                               |
| description | String | no                   | The description of the image, used for the description in the opened Lightbox (if showDescription = true).                                                                                    |
| alt         | String | no (but recommended) | The alt text of the image, used for the description text of the image in the opened Lightbox, if no description is available. Also used if the Picture can't get loaded or for Screenreaders. |

## Demo

See also the Demo on [CodeSandbox](https://codesandbox.io/s/svelte-photoswipe-gallery-czmreq?file=/App.svelte).
