<script context="module">
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>
<!-- Button for New Post -->
<script>
	import Button from "../../components/Button.svelte";
	import { goto } from '@sapper/app';
	export let posts;
	let NewPost = 'New Post';

	function clickEvent(){
		NewPost = 'Fake Post';
		console.log ('it works');
		goto('./routes/CreatePost.svelte');
	}
</script>

<style>
	ul {
		margin: 0 0 1em 0;
		line-height: 1.5;
	}
</style>

<svelte:head>
	<title>Blog</title>
</svelte:head>

<h1>Recent posts</h1>
<h1>{NewPost}</h1>


<Button on:click = {clickEvent}>Click me</Button>

<ul>
	{#each posts as post}
		<!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
		<li><a rel='prefetch' href='blog/{post.slug}'>{post.title}</a></li>
	{/each}
</ul>