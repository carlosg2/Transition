<script lang="ts" context="module">
    import { fade } from "svelte/transition";
    import { crossfade } from "./crossfade";
    import { circOut } from 'svelte/easing';
    import * as eases from 'svelte/easing';

    let [ send, receive ] = crossfade({
        fallback: (node, params, flyingTo) => fade(node, {
            ...params,
            duration: 300,
            delay: flyingTo ? 200 : 0
        }),
        delay: 0,
        easing: eases.expoOut,
        duration: (d) => Math.max(0, 400)
    });
</script>

<script lang="ts">
    export let src;
    let className = ''
    export { className as class };

    export let alt = "";

    export let transitionId;

</script>

<style>
    .container {
        position: relative;
    }

    .imgWrapper {
        position: absolute;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
</style>

<div class="container {className}">
    <div class="imgWrapper" out:send="{{key: transitionId}}" in:receive="{{key: transitionId}}">
        <img src="{src}" alt="{alt}" crossorigin='anonymous'/>
    </div>
</div>