<script>
	import TransitionableImage from './TransitionableImage.svelte';
</script>

<div class="container">
    <a href="/a">
        <TransitionableImage class="image" src='https://picsum.photos/id/400/1200/800' transitionId="a"/>
    </a>
    <a href="/b">
        <TransitionableImage class="image" src='https://picsum.photos/id/402/1200/800' transitionId="b"/>
    </a>
    <a href="/c">
        <TransitionableImage class="image" src='https://picsum.photos/id/403/1200/800' transitionId="c"/>
    </a>
    <a href="/d">
        <TransitionableImage class="image" src='https://picsum.photos/id/404/1200/800' transitionId="d"/>
    </a>
    <a href="/e">
        <TransitionableImage class="image" src='https://picsum.photos/id/405/1200/800' transitionId="e"/>
    </a>
</div>


<style>
    .container {
        display: flex;
        flex-direction: row;
        gap: 20px;
        width: 100%;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .container :global(.image) {
        aspect-ratio: 4 / 12;
        width: 180px;
        flex-shrink: 0;
        align-items: center;
        object-fit: cover;
    }
</style>
