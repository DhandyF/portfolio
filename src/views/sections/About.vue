<template>
<section
	id="about"
	class="mb-16 md:mb-24 lg:mb-36 scroll-mt-16 lg:scroll-mt-24"
>
	<div class="mb-4 py-4 lg:sr-only">
		<h2 class="text-sm text-bold text-slate-200">ABOUT</h2>
	</div>
	<p
		v-for="paragraph in about.paragraph"
		class="text-slate-400 leading-7 mb-4"
	>
		{{ paragraph }}
	</p>
</section>
</template>

<script setup>
import { ref } from 'vue'
import { ABOUT } from '@/lib/statics'

const about = ref(ABOUT)
</script>
