<script setup>
import {ArrowRightIcon, ChevronDoubleDownIcon} from '@heroicons/vue/solid'
</script>
<template>
	<section class="bg-gray-300 flex flex-col justify-center items-center md:px-20 min-h-screen">
		<div class="flex flex-col w-full py-12 px-4 lg:px-0 justify-center items-center">
			<p class="text-2xl text-gray-800 font-medium">很高興認識你！我是<span class="text-black">李柔霈</span></p>
			<h1 class="text-7xl text-left text-gray-800 mt-1 font-extrabold">
        專業自介網站設計師
			</h1>
			<p class="text-lg text-gray-600 font-light pt-8">
        You can also call me 09 :D
			</p>
			<a
				href="#contact"
				class="mt-3 flex items-center text-xl font-regular pb-2">
				歡迎聯絡我呀❤
			</a>
		</div>

		<a href="#activities" class="animate-bounce cursor-pointer">
			<chevron-double-down-icon class="w-16 h-20"/>
		</a>
	</section>
</template>
