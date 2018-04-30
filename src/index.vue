<template>
	<div class="lds-ellipsis" :style="`width: ${scale}px; height: ${cs(11)}px;`">
    <div :style="`background: ${bg}; width: ${cs(11)}px; height: ${cs(11)}px; left: ${cs(6)}px;`"/>
    <div :style="`background: ${bg}; width: ${cs(11)}px; height: ${cs(11)}px; left: ${cs(6)}px;`"/>
    <div :style="`background: ${bg}; width: ${cs(11)}px; height: ${cs(11)}px; left: ${cs(26)}px;`"/>
    <div :style="`background: ${bg}; width: ${cs(11)}px; height: ${cs(11)}px; left: ${cs(45)}px;`"/>
	</div>
</template>

<script>
	export default {
		props: {
			scale: {
				default: 64,
				type: Number
			},
			bg: {
				default: '#fff',
				type: String
			}
		},
		methods: {
			/* Calc new loading size */
			cs(b) {
				return this.scale * b / 64
			}
		}
	}
</script>

<style>
	.lds-ellipsis {
	  display: inline-block;
	  position: relative;
	}
	.lds-ellipsis div {
	  position: absolute;
	  border-radius: 50%;
	  animation-timing-function: cubic-bezier(0, 1, 1, 0);
	}
	.lds-ellipsis div:nth-child(1) {
	  animation: lds-ellipsis1 0.6s infinite;
	}
	.lds-ellipsis div:nth-child(2) {
	  animation: lds-ellipsis2 0.6s infinite;
	}
	.lds-ellipsis div:nth-child(3) {
	  animation: lds-ellipsis2 0.6s infinite;
	}
	.lds-ellipsis div:nth-child(4) {
	  animation: lds-ellipsis3 0.6s infinite;
	}
	@keyframes lds-ellipsis1 {
	  0% { transform: scale(0); }
	  100% { transform: scale(1); }
	}
	@keyframes lds-ellipsis3 {
	  0% { transform: scale(1); }
	  100% { transform: scale(0); }
	}
	@keyframes lds-ellipsis2 {
	  0% { transform: translate(0, 0); }
	  100% { transform: translate(19px, 0); }
	}
</style>