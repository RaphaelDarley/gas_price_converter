<script>
	let USDperMMBTU = 1; //
	const EUROperMWhRatio = 3.328304;
	$: EUROperMWh = USDperMMBTU * EUROperMWhRatio;
	const GBPperThermRatio = 8.252829;
	$: GBpperTherm = USDperMMBTU * GBPperThermRatio;

	let test3 = 0;
	$: test4 = test3 * 2;

	function setVal(value) {
		USDperMMBTU = value;
	}
</script>

<main>
	<h1>Gas price converter</h1>

	<label for="USDperMMBTU">USD/MMBTU: </label>
	<input
		type="text"
		name="USDperMMBTU"
		id="USDperMMBTU"
		bind:value={USDperMMBTU}
		on:input={setVal(USDperMMBTU)}
	/>

	<label for="EUROperMWh">Euro/MWh: </label>
	<input
		type="text"
		name="EUROperMWh"
		id="EUROperMWh"
		bind:value={EUROperMWh}
		on:input={setVal(EUROperMWh / EUROperMWhRatio)}
	/>

	<label for="GBpperTherm">GBP pence/Therm: </label>
	<input
		type="text"
		name="GBpperTherm"
		id="GBpperTherm"
		bind:value={GBpperTherm}
		on:input={setVal(GBpperTherm / GBPperThermRatio)}
	/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
