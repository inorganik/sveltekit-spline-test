<script lang="ts">

  import { Application } from '@splinetool/runtime';
  import { onMount } from 'svelte';
  import scene from '$lib/spline/scene.splinecode';

  let canvasEl = $state<HTMLCanvasElement>()
  let splineApp = $state<Application>() 

  onMount(() => {
    if (canvasEl) {
      splineApp = new Application(canvasEl);
      splineApp.load(scene)
    }
  });
</script>

<div class="m-auto w-[410px] h-[410px] border-2 border-black">
  <canvas class="w-full h-full" bind:this={canvasEl}></canvas>
</div>
