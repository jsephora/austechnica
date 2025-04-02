<script setup>
import TemplatePackages from "@/components/Home/TemplatePackages.vue";
import ThemeController from "@/components/Home/ThemeController.vue";
import ComponentsPreview from "@/components/Home/ComponentsPreview.vue";
import Guide from "@/components/Home/Guide.vue";
import CurrencyConverter from '@/components/CurrencyConverter.vue';


const title = document.title;
const currentHostname = window.location.hostname;
</script>

<template>
	<!-- Feature section with product screenshot -->
	<div class="overflow-hidden py-24 sm:py-32">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div
				class="mx-auto grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 sm:gap-y-20 lg:mx-0 lg:max-w-none lg:grid-cols-2">
				<div class="lg:pt-4 lg:pr-8">
					<div class="lg:max-w-lg">
						<h2 class="text-base/7 font-semibold">Deploy faster</h2>
						<p class="mt-2 text-4xl font-semibold tracking-tight text-pretty sm:text-5xl">A
							better workflow</p>
						<p class="mt-6 text-lg/8">Lorem ipsum, dolor sit amet consectetur adipisicing
							elit. Maiores impedit perferendis suscipit eaque, iste dolor cupiditate blanditiis ratione.
						</p>
						<br>
						<!-- GitHub -->
						<button class="btn bg-black text-white border-black">
							<svg aria-label="GitHub logo" width="16" height="16" xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 24 24">
								<path fill="white"
									d="M12,2A10,10 0 0,0 2,12C2,16.42 4.87,20.17 8.84,21.5C9.34,21.58 9.5,21.27 9.5,21C9.5,20.77 9.5,20.14 9.5,19.31C6.73,19.91 6.14,17.97 6.14,17.97C5.68,16.81 5.03,16.5 5.03,16.5C4.12,15.88 5.1,15.9 5.1,15.9C6.1,15.97 6.63,16.93 6.63,16.93C7.5,18.45 8.97,18 9.54,17.76C9.63,17.11 9.89,16.67 10.17,16.42C7.95,16.17 5.62,15.31 5.62,11.5C5.62,10.39 6,9.5 6.65,8.79C6.55,8.54 6.2,7.5 6.75,6.15C6.75,6.15 7.59,5.88 9.5,7.17C10.29,6.95 11.15,6.84 12,6.84C12.85,6.84 13.71,6.95 14.5,7.17C16.41,5.88 17.25,6.15 17.25,6.15C17.8,7.5 17.45,8.54 17.35,8.79C18,9.5 18.38,10.39 18.38,11.5C18.38,15.32 16.04,16.16 13.81,16.41C14.17,16.72 14.5,17.33 14.5,18.26C14.5,19.6 14.5,20.68 14.5,21C14.5,21.27 14.66,21.59 15.17,21.5C19.14,20.16 22,16.42 22,12A10,10 0 0,0 12,2Z">
								</path>
							</svg>
							Login with GitHub
						</button>
						<dl class="mt-10 max-w-xl space-y-8 text-base/7 text-gray-600 lg:max-w-none">
							<div v-for="feature in features" :key="feature.name" class="relative pl-9">
								<dt class="inline font-semibold text-gray-900">
									<component :is="feature.icon" class="absolute top-1 left-1 size-5 text-indigo-600"
										aria-hidden="true" />
									{{ feature.name }}
								</dt>
								{{ ' ' }}
								<dd class="inline">{{ feature.description }}</dd>
							</div>
						</dl>
					</div>
				</div>
				<img src="https://tailwindcss.com/plus-assets/img/component-images/dark-project-app-screenshot.png"
					alt="Product screenshot"
					class="w-[48rem] max-w-none rounded-xl ring-1 shadow-xl ring-gray-400/10 sm:w-[57rem] md:-ml-4 lg:-ml-0"
					width="2432" height="1442" />
			</div>
		</div>
	</div>



	<!-- Packages -->
	<div class="bg-base-300 text-base-content text-center mb-10">
		<div class="container-center pb-4">
			<TemplatePackages />
		</div>
	</div>

		<!-- Currency Converter -->
	<div class="bg-base-900 text-base-content text-center mb-10">
		<div class="container-center pb-4">
			<currency-converter />
		</div>
	</div>

	<!-- Theme Controller -->
	<div class="container-center text-center">
		<ThemeController class="mb-10" />
	</div>

</template>

<style scoped lang="scss"></style>