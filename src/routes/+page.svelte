<script>
let rows = []
let score = 0;
let gameover = false;

function generateRow() {
	let row = new Array(4).fill("white");
	let pos = Math.trunc(Math.random()*4);
	row[pos] = "black"
return row;
}

function fillRow(){
	for(let i = 0; i < 4; i++){
	rows.push(generateRow());
	}
}
	
fillRow()

</script>

<style>
.app {
	position: flex;
	top: 0px;
	left: 50%;
	transform: translateX(-50%);
	width: 100%;
	height: 100%;
	max-width: 400px;
}

.app .header {
	position: sticky;
	top: 0px;
	left: 0px;
	width: 100%;
	height: 50px;
	background: #0badea;
	display: flex;
	justify-contnent: space-between;
	align-items: center;
	padding: 0px 20px;
	color: #fff;
}
.app .game{
	width: 100%;
	height: calc(100% - 50px);
	background: #fff;
}

.app .game .row{
	display: flex;
	width: 100%;
	height: calc(100% / 4);
}

.app .game .row .box {
	flex: 1;
	border: 1px solid #555;
	cursor: pointer;
}

</style>

<link rel="stylesheet" href="../global.css">

<main class="app">
	<div class="header">
	<h4> PianoTiles </h4>
	<p> Score: {score} </p>
	</div>
	<div class="game">
    {#each rows as row, i}
	<div class="row">
	{#each row as box, j}
	<div class={"box"+box}>
	</div>
	{/each}
	</div>
	{/each}
	</div>
</main>
