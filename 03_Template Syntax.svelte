<script>
	const expression = 1;
	const promise = 1;
	const value = 1;
	const items = [];
</script>

<h3>if example</h3>
{#if expression}
	<!-- if -->
{:else if expression}
	<!-- else if -->
{:else}
	<!-- else -->
{/if}

<h3>each example</h3>
{#each items as item}
	<!-- {item} -->
{/each}

<h3>await example</h3>
{#await promise}
	<!-- promise is pending -->
{:then value}
	<!-- promise was fulfilled -->
	<!-- {value} -->
{:catch error}
	<!-- promise was rejected -->
	<!-- {error.message} -->
{/await}

<h3>key example</h3>
{#key value}
	<!-- {value} -->
{/key}
