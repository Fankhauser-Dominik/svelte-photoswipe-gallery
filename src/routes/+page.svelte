<script lang="ts">
	import PhotoswipeGallery from '$lib/PhotoswipeGallery.svelte';

	const images = [
		{
			src: 'https://placebear.com/1920/1080',
			height: 1080,
			width: 1920,
			alt: 'Test',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
		},
		{
			src: 'https://placebear.com/600/400',
			width: 600,
			height: 400,
			description: '<a href="https://google.com">Google</a>'
		},
		{
			src: 'https://placebear.com/400/400',
			width: 4000,
			height: 4000,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit2',
			alt: 'Random'
		},
		{
			src: 'https://placebear.com/1920/1080',
			preview: 'https://placebear.com/400/400',
			width: 1920,
			height: 1080,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit3',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit4',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit5',
			alt: 'Random'
		},
		{
			src: 'https://placebear.com/600/400',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit1'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 600,
			height: 400,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 400,
			height: 600,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 800,
			height: 1200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		},
		{
			src: 'https://source.unsplash.com/random',
			width: 300,
			height: 200,
			description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
			alt: 'Random'
		}
	];
</script>

<PhotoswipeGallery {images} />
