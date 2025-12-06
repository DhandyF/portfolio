<template>
	<nav class="navbar hidden lg:block">
		<ul class="mt-16 w-max">
			<li v-for="menu in menus" :key="menu.key" class="flex items-center py-3 cursor-pointer text-slate-500"
				@mouseenter="onFocus(menu)" @mouseleave="onLeave()" @click="onClick(menu)">
				<span class="mr-4 h-px w-8 bg-slate-600 transition-all motion-reduce:transition-none" :class="[
					{ '!w-16 !bg-slate-200': isActiveMenu(menu) }
				]" />
				<span class="nav-text text-xs font-bold uppercase tracking-widest"
					:class="[{ '!text-slate-200': isActiveMenu(menu) }]">
					{{ menu.title }}
				</span>
			</li>
		</ul>
	</nav>
</template>
	
<script setup>
import { onMounted, ref, onBeforeUnmount } from 'vue';

const menus = [
	{ key: 'about', title: 'About' },
	{ key: 'experience', title: 'Experience' },
	// { key: 'project', title: 'Project' },
];

const focusedMenu = ref(null);
const activeMenu = ref(null); // store string key, e.g. 'about' or 'experience'

// click: set activeMenu to the key string and smooth scroll
const onClick = (menu) => {
	activeMenu.value = menu.key;
	const el = document.getElementById(menu.key);
	if (el) el.scrollIntoView({ behavior: 'smooth' });
};

const onFocus = (menu) => {
	focusedMenu.value = menu;
};
const onLeave = () => {
	focusedMenu.value = null;
};

const isHoveredMenu = (menu) => {
	return menu.key === focusedMenu?.value?.key;
};
const isActiveMenu = (menu) => {
	return menu.key === activeMenu?.value || isHoveredMenu(menu);
};

let observer = null;

onMounted(() => {
	const options = {
		root: null,
		rootMargin: '0px 0px -30% 0px',
		threshold: 0.25,
	};

	const callback = (entries) => {
		entries.forEach(entry => {
			if (entry.isIntersecting) {
				const target = entry.target;
				if (target.closest && target.closest('#experience')) {
					activeMenu.value = 'experience';
				} else if (target.id) {
					activeMenu.value = target.id;
				}
			}
		});
	};

	observer = new IntersectionObserver(callback, options);

	document.querySelectorAll('section[id]').forEach(section => {
		observer.observe(section);
	});

	const experienceSection = document.getElementById('experience');
	if (experienceSection) {
		experienceSection.querySelectorAll('li').forEach(li => {
			observer.observe(li);
		});
	}
});

onBeforeUnmount(() => {
	if (observer) {
		observer.disconnect();
		observer = null;
	}
});
</script>
