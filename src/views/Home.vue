<template>
<div
	id="home"
	class="min-h-screen max-w-7xl mx-auto text-white px-6 py-12 md:px-12 md:py-16 lg:py-0">
	<div class="lg:flex lg:justify-between lg:gap-4">
		<Header />
		<Main />
	</div>
</div>
</template>

<script setup>
import Header from '@/components/Header.vue';
import Main from '@/views/Main.vue';

</script>
