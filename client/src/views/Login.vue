<script setup>
import {loadStytch} from '@stytch/stytch-js'
import { onMounted } from 'vue'

const setup = async () => {
	const Stytch = await loadStytch()

	let stytch = Stytch("public-token-test-2e21111b-02b5-4c03-8815-a01353e5e3f3").mount({
		elementId: "#gonetap",
		loginOrSignupView: {
			products: ['oauth'],
			oauthOptions: {
				providers: [
					{
						type: 'google', 
						'one_tap': true,
						position: 'embedded',
					}
				]
			},
		},
		style: {
			width: 'calc(100% - 20px)'
		}
	})

	console.log(stytch);
}

onMounted(() => {
	setup()
})
</script>

<template>
	<main class="login min-h-screen bg-gradient-to-br from-green-500 to-cyan-400">
		<section class="container mx-auto pt-16 pb-4 px-4">
			
			<h1 class="text-4xl mb-8 text-center font-black uppercase">Password-less Login</h1>

			<div class="bg-gray-700 max-w-md mx-auto rounded p-4">
				<div id="gonetap"></div>
			</div>

		</section>
	</main>
</template>