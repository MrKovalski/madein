<script>
	import Quagga from 'quagga';

	import cbe from './static/data/countrybyean.json';
	let prvaTri = "";
	let barcode = "";
	let zemljaText = "Neutvrđeno";

	function prepoznajZemlju(){
		let zo = cbe.map(el => el.barcode);
		let zoi = zo.indexOf(barcode)
		
		if(barcode.toString().length === 3){
			zemljaText = barcode.toString().length;
		} else{
			zemljaText = "Unesi tri broja";
		}
	}
</script>

<main>
	<h1>Odakle potiče proizvod?</h1>
	<h3>Unesi prva tri broja barkoda</h3>
	<div id="bc-container">
		<form action="javascript:void(0);">
			<input on:keyup={prepoznajZemlju} id="input-barkod" type="number" placeholder="Barkod..." bind:value={barcode}>
		</form>
		<p id="zemlja-text">{zemljaText}</p>
	</div>
</main>

<style>
	
main{
	margin: 0 auto;
	width: 100vw;
}
h1 {
	text-transform: uppercase;
	font-size: 2em;
	text-align: center;
}
h3 {
	margin-top: 2em;
	text-transform: uppercase;
	font-size: 1.2em;
	text-align: center;
}
#bc-container{
	margin: 0 auto;
	display: grid;
	grid-template-columns: 1fr;
	justify-items: center;
}
#input-barkod{
	border-radius: 0.5em;
	border: 0.2em solid black;
	
}
#zemlja-text{
	background-color: rgb(160, 235, 160);
	padding: 0.5em 1em;
	font-size: 2em;
	width: 50%;
	margin-bottom: 1em;
	text-align: center;
	text-transform: uppercase;
	font-weight: 600;
}



input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
input[type=number] {
    -moz-appearance: textfield;
}
</style>