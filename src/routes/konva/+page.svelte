<script lang="ts">
	import * as fabric from 'fabric';

	const { data } = $props();

	const options: any = {
		width: 1080,
		height: 1920,
		preserveObjectStacking: true,
		renderOnAddRemove: false,
		controlsAboveOverlay: true,
		allowTouchScrolling: true,
		enableRetinaScaling: false
		// backgroundColor: 'black'
	};

	// fabric.FabricObject.prototype.objectCaching = false;

	let fabricCanvas;

	$effect(() => {
		fabricCanvas = new fabric.Canvas('original-canvas', options);

		let rect = new fabric.Rect({
			left: 120,
			top: 10,
			fill: 'teal',
			width: 150,
			height: 150,
			angle: 45
		});
		fabricCanvas.add(rect);
		fabricCanvas.renderAll();
	});
</script>

<!-- <canvas id="canvas" width="1080" height="1920"></canvas> -->

<canvas id="original-canvas" width="1080" height="1920"></canvas>
<div id="konva-container" class="mt-4"></div>
