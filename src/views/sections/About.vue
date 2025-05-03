<template>
<div id="about" class="mb-16 md:mb-24 lg:mb-36 text-slate-500">
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
