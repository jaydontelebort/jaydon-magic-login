<script>
	import supabase from '$lib/db';

	async function signOut() {
		const { error } = await supabase.auth.signOut();
		if (error) alert(error.message);
	}
</script>

<h1>Welcome!</h1>

<button on:click={signOut}>Logout</button>
