<script>
  import { page } from '$app/stores';
  import { fade } from 'svelte/transition';
  import TransitionableImage from '../TransitionableImage.svelte';

  let { id } = $page.params;

  const images = {
    a: 'https://picsum.photos/id/400/1200/800',
    b: 'https://picsum.photos/id/402/1200/800',
    c: 'https://picsum.photos/id/403/1200/800',
    d: 'https://picsum.photos/id/404/1200/800',
    e: 'https://picsum.photos/id/405/1200/800'
  }

  let src = images[id];
</script>

<style>
    .container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        height: 100vh;
    }
    .imgContainer {
        width: 100vw;
        height: 100%;
        border-radius: 20px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        flex-shrink: 0;
    }
    .imgContainer > :global(.image) {
        height: 840px;
        aspect-ratio: 8 / 6;
    }

    /* .content {
        display: flex;
        flex-direction: column;
        flex-grow: 1;
        padding: 0 400px 0 60px;
        justify-content: center;
        font-family: sans-serif;
        
    }

    .content > p {
        margin-top: 30px;
    } */
</style>

<div class="container">
    <a class="imgContainer" href="/">
        <TransitionableImage class="image" src={src} transitionId={id}/>
    </a>
    
</div>