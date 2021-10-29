<script>
	import supabase from '$lib/db';

	let email;

	async function loginUser() {
		const { error } = await supabase.auth.signIn({
			email
		});

		if (error) alert(error.message);
	}
</script>

<h1 class="bg-primary text-white p-5 text-center">Homepage</h1>

<div class="text-center">
	<form on:submit|preventDefault={loginUser}>
		<label for="email">Email</label>
		<input id="email" bind:value={email} type="email" />

		<button>Magic</button>
	</form>
</div>
