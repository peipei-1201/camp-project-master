<script setup>
import {PhoneIcon, MailIcon} from '@heroicons/vue/outline';
import {ref} from "vue";
import axios from 'axios'
import Swal from 'sweetalert2'

const name = ref('');
const email = ref('');
const message = ref('');

const submit = () => {
	const access_key = '49ef17a0-8a59-40c9-b861-65ccc0edc090'
	axios.post('https://api.web3forms.com/submit', {
		access_key,
		email: email.value,
		name: name.value,
		message: message.value
	}).then(res => {
		if (res.status === 200) {
			Swal.fire({
				title: '感謝您的來信',
				text: '我們會盡快回覆您',
				icon: 'success',
				confirmButtonText: '確定'
			})
		}
	})
}
</script>
<template>
	<div id="contact" class="flex flex-col lg:flex-row bg-gray-500 pt-32 md:pb-32 md:px-20">
		<div class="py-10 lg:w-2/5 text-white px-8 xl:px-0 flex flex-col gap-4">
			<h1 class="text-4xl font-bold">Contact Me :)</h1>
			<p class="text-xl font-normal lg:pr-4">
				可以透過下列資訊或聯絡表單聯絡我呦~
			</p>
			<div>
				<div class="flex items-center gap-4">
					<div>
						<PhoneIcon class="w-6 h-6"/>
					</div>
					<p>0903012429</p>
				</div>
        <div class="flex items-center gap-4 mt-3">
          <div>
            <PhoneIcon class="w-6 h-6"/>
          </div>
          <p>𝑳𝒊𝒏𝒈𝑱𝒊𝒖#4177</p>
        </div>
				<div class="flex items-center gap-4 mt-3">
					<div>
						<MailIcon class="w-6 h-6"/>
					</div>
					<p>pei931201@gmail.com</p>
				</div>
			</div>
		</div>
		<div class="bg-gray-200 h-full lg:w-3/5 p-3 rounded-t-xl md:rounded-xl">
			<div class="bg-white py-4 px-8 rounded-xl">
				<h1 class="text-4xl text-gray-800 font-extrabold mb-6">聯絡表單</h1>
				<form class="block w-full flex flex-col items-start" @submit.prevent="submit">
					<label
						class="text-gray-800 text-sm"
						for="name">名字</label>
					<input id="name"
					       type="text"
					       class="w-full focus:outline-none focus:border focus:border-indigo-700 font-normal h-10 flex items-center pl-3 text-sm border-gray-300 rounded border"
					       placeholder="Please enter your name"
					       v-model="name"
					/>

					<label class="text-gray-800 text-sm mt-4"
					       for="Email">電子郵件</label>
					<input id="Email"
					       type="email"
					       class="w-full focus:outline-none focus:border focus:border-indigo-700 font-normal h-10 flex items-center pl-3 text-sm border-gray-300 rounded border"
					       placeholder="Please enter your e-mail"
					       v-model="email"
					/>

					<label class="text-gray-800 text-sm mt-4"
					       for="message">訊息</label>
					<textarea id="message"
					          class="w-full border-gray-300 border mb-4 rounded py-2 text-sm outline-none resize-none px-3 focus:border focus:border-indigo-700"
					          placeholder="Please enter what message do you want to send to me"
					          rows="8"
					          v-model="message"
					></textarea>

					<button
						class="self-center bg-gray-800 hover:bg-indigo-600 rounded text-white px-8 py-3 text-sm">
						送出
					</button>
				</form>
			</div>
		</div>
	</div>
</template>
