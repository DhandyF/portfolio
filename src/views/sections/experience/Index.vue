<template>
<section
	id="experience"
	class="mb-16 md:mb-24 lg:mb-36 scroll-mt-16 lg:scroll-mt-24"
>
	<div class="mb-4 py-4 lg:sr-only">
		<h2 class="text-sm text-bold text-slate-200">EXPERIENCES</h2>
	</div>
	<ol>
		<li
			v-for="experience in EXPERIENCES"
			:key="experience.id"
			class="mb-12 cursor-pointer lg:p-3 rounded-lg group hover:bg-white/10"
		>
			<a :href="experience.url" target="_blank">
				<div class="grid sm:grid-cols-8 sm:gap-8 md:gap-4">
					<div class="z-10 mb-2 mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500 sm:col-span-2">
						{{ experience.period }}
					</div>
					<div class="sm:col-span-6">
						<h3 class="font-medium text-slate-200 mb-2 group-hover:!text-teal-300">
							<a href="">
								<span>{{ experience.position }} · {{ experience.company }}</span>
							</a>
						</h3>
						<p class="text-slate-400 text-sm leading-[1.5] mb-2">
							{{ experience.job_desc }}
						</p>
						<ul class="flex flex-wrap">
							<li
								v-for="(tech, index) in experience.tech_stack"
								:key="tech + index"
								class="items-center rounded-full text-xs text-teal-300 bg-teal-400/10 py-1 px-3 mr-1 mt-2"
							>
								{{ tech }}
							</li>
						</ul>
					</div>
				</div>
			</a>
		</li>
	</ol>
</section>
</template>

<script setup>
import { EXPERIENCES } from '@/lib/statics'
</script>
