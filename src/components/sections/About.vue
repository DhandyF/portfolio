<template>
<div id="about" class="text-slate-500">
	<div class="mb-4 py-4 lg:sr-only">
		<h2 class="text-sm text-bold text-slate-200">ABOUT</h2>
	</div>
	<p>
		{{ ABOUT }}
	</p>
</div>
</template>

<script setup>
import { ABOUT } from '@/lib/statics';
</script>
