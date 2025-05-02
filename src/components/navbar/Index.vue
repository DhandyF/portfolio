<template>
<nav class="navbar hidden lg:block">
	<ul class="mt-16 w-max">
		<li
			v-for="menu in menus"
			:key="menu.key"
			class="flex items-center py-3 cursor-pointer text-slate-500"
			@mouseenter="onFocus(menu)"
			@mouseleave="onLeave()"
			@click="onClick(menu)"
		>
			<span
				class="mr-4 h-px transition-all motion-reduce:transition-none"
				:class="getDynamicClass(menu)"
			/>
			<span
				class="nav-text text-xs font-bold uppercase tracking-widest"
				:class="[{ 'text-slate-200': isActiveMenu(menu) }]"
			>
				{{ menu.title }}
			</span>
		</li>
	</ul>
</nav>
</template>

<script setup>
import { ref } from 'vue'

const menus = [
	{
		key: 'about',
		title: 'About',
	},
	{
		key: 'experience',
		title: 'Experience',
	},
	{
		key: 'project',
		title: 'Project',
	},
];

const focusedMenu = ref(null)
const activeMenu = ref(null)

const onClick = (menu) => {
	activeMenu.value = menu
}

const onFocus = (menu) => {
	focusedMenu.value = menu
}

const onLeave = () => {
	focusedMenu.value = null
}

const isHoveredMenu = (menu) => {
	return menu.key === focusedMenu?.value?.key
}

const isActiveMenu = (menu) => {
	return menu.key === activeMenu?.value?.key || isHoveredMenu(menu)
}

const getDynamicClass = (menu) => {
	return isActiveMenu(menu) ? 'w-16 bg-slate-200' : 'w-8 bg-slate-600';
}
</script>
