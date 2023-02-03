<template>
	<div
		@dragenter.prevent="toggleActive"
		@dragleave.prevent="toggleActive"
		@dragover.prevent
		@drop.prevent="toggleActive"
		:class="{ 'active-dropzone': active }"
		class="dropzone"
	>
		<span>Drag or Drop File</span>
		<span>OR</span>
		<label for="dropzoneFile">select File</label>
		<input type="file" class="dropzoneFile" id="dropzoneFile" />
	</div>
</template>

<script setup>
import { ref } from 'vue'

const active = ref(false)

function toggleActive() {
	active.value = !active.value
}
</script>

<style scoped>
.dropzone {
	width: 400px;
	height: 200px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	row-gap: 16px;
	border: 2px dashed #41b883;
	background-color: #fff;
	transition: 0.3s ease all;
}

label {
	padding: 8px 12px;
	color: #fff;
	background-color: #41b883;
	transition: 0.3s ease alll;
}

input {
	display: none;
}

.active-dropzone {
	color: #fff;
	border-color: #fff;
	background-color: #41b883;
}

.active-dropzone label {
	background-color: #fff;
	color: #41b883;
}
</style>
