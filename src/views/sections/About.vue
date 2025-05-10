<template>
<section
	id="about"
	class="mb-16 md:mb-24 lg:mb-36 scroll-mt-16 lg:scroll-mt-24"
>
	<div class="mb-4 py-4 lg:sr-only">
		<h2 class="text-sm text-bold text-slate-200">ABOUT</h2>
	</div>
	<p class="text-slate-400">
		{{ ABOUT }}
	</p>
</section>
</template>

<script setup>
import { ABOUT } from '@/lib/statics';
</script>
