<template>
	<div>
		<p v-text="mytext"></p>
		<button @click="generateKey">Generate</button>	
		<div class="border" v-text="encryptedKey"></div>

		<hr>
		<!-- Kf/iuUG3ucwh7HGnMvZqlstYaw3xemZ0ut5xzNVdvDom+DO/TyxUw6fSlmZHthwN6gCk7cYmJrOOuUol0SUJqLzfhTl7v0OzmNAzTxVumelkE/z/pNYLalMCxTlilJp2niDQUXm/27RnV1JlgIvv7dc/3vEqXNsoqeDihGw0n5U= -->
		<input type="text" name="" v-model="myEncryptedKey">
		<button @click="decryptIt"></button>

		<p>DECRYPTED:</p>
		<p v-text="myDecryptedKey"></p>
	</div>
</template>
<script>
	import jsencrypt from 'jsencrypt'
	export default {
		data() {
			return {
				mytext: 'MOOse',
				encryptedKey: '__UNKNOWN__',
				myEncryptedKey: '',
				myDecryptedKey: '',
			}
		},
		methods: {
			// HOW TO DO IT
			// https://www.npmjs.com/package/jsencrypt
			generateKey() {
				let generator = new jsencrypt()
				this.encryptedKey = generator.encrypt('MY-TEST-PUBLIC-KEY')
				// console.log(generator)
			},

			decryptIt() {
				var generator = new jsencrypt();
          		generator.setPrivateKey(this.myEncryptedKey);
          		var uncrypted = decrypt.decrypt(encrypted);
			}
		}
	}
</script>
<style>
	.border {
		border: 2px solid purple;
	}
</style>