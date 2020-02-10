<template>
	<div class="div-square">
		<h2>{{brand}}</h2>
		<div class="square">
			<p>Overdue Trans.</p>
			<p class="number" :class=firstColor>{{firstNumber}}</p>
			<p>% RTF</p>
			<p class="number" :class=secondColor>{{secondNumber}}</p>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Square',
		props: {
			firstColor: String,
			secondColor: String,
			brand: String,
			firstNumber: Number,
			secondNumber: String
		}
	}
</script>

<style>
h2 {
  font-size: 13px;
  text-align: center;
  margin-bottom: 1%;
}

.div-square {
  width: 30%;
  margin: 5% 10%;
}

.square {
  background-color: #3A3736;
  border: 1px solid #BCB7B7;
  border-radius: 10px;
  width: 100%;
  color: #fff;
  text-align: center;
  padding: 7% 0;
}

.square p:first-child {
  margin-top: 0;
}

.number {
  font-size: 30px;
  margin: 1%;
  font-weight: 600;
}

.green {
  color: #85BC41;
}

.red {
  color: #E93325;
}

.yellow {
  color: #EBB43E;
}
</style>