<template>
	<header class="lg:sticky lg:top-0 lg:max-h-screen lg:w-[45%] lg:flex lg:flex-col lg:justify-between lg:py-24 font-[Noto Sans]">
		<div>
			<h1 class="text-4xl sm:text-5xl font-bold text-slate-200">
				{{ FULL_NAME }}
			</h1>
			<h3 class="text-xl mt-3 text-slate-200">
				{{ JOB_ROLE }}
			</h3>
			<p class="mt-4 max-w-xs text-slate-400">{{ ROLE_OVERVIEW }}</p>
			<nav-bar />
		</div>
		<social-media />
	</header>
</template>

<script setup>
import NavBar from '@/components/navbar/Index.vue';
import SocialMedia from '@/components/SocialMedia.vue';

import {
	FULL_NAME,
	JOB_ROLE,
	ROLE_OVERVIEW
} from '@/lib/statics';

</script>
