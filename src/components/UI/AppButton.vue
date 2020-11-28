<template>
  <button
    class="btn accent"
    :disabled="disabled"
    v-bind="$attrs"
    v-on="$listeners"> <slot /> </button>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    disabled: {
      type: Boolean,
      default: false
    }
  }
}
</script>


<style lang="scss">
@import '@/scss/variables.scss';

.btn {
	display: flex;
	align-items: center;
  color: rgb(255, 255, 255);
	border: none;
	border-radius: 3px;
	height: 40px;
	cursor: pointer;
  transition: all 150ms ease-out;
	&:focus {
		outline: none;
	}
	&:disabled {
		opacity: 0.5;
	}

	img {
		width: 28px;
		margin: 0 3px;
		transition: all 150ms ease-out;
	}
	span {
		margin: 0 10px;
	}
}

.accent {
	background-color: #0074D9;
	&:hover:not(:disabled) {
		background-color: #001f3f;
	}
}

.danger {
  background-color: #39CCCC;
	&:hover:not(:disabled) {
		background-color: #001f3f;
	}
	&:disabled {
		background-color: $danger-low;
	}
}

.info {
  background-color:  #457B9D;
	&:hover:not(:disabled) {
		background-color: $secondary;
	}
}

.warning {
  background-color: #1D3557;
	&:hover:not(:disabled) {
		background-color: #1D3557;
	}
}

.white {
  background-color: rgba(255, 255, 255, 0.65);
	color: #000000;
	&:hover:not(:disabled) {
		background-color: #ffffff;
	}
}

.hover {
	position: absolute;
	right: 10px;
	width: 55px;
	height: 50px;
	background-color: $dark-low;
	// border: solid 1px $dark-low;
	overflow: hidden;
	transition: all 300ms ease-out;
	&:hover {
		width: 170px;
		span {
			text-align: center;
			opacity: 1;
		}
	}
	img {
		width: 30px;
		margin: 5px;
	}
	span {
		position: absolute;
		opacity: 0;
		top: 50%;
		transform: translateY(-50%);
		width: 100%;
		transition: all 300ms ease-out;
	}
}
</style>
