<template>
	<div class="primary">
		<Core />
    </div>
</template>

<script>
import Card from '~/components/Card'
import NuxtLogo from '~/components/NuxtLogo.vue'
import NavBar from '../components/NavBar.vue'
import Footer from '../components/Footer.vue'
import Core from '../components/Core.vue'

export default {
	name: 'IndexPage',
	components: {
    Card,
	NuxtLogo,
    NavBar,
	Footer,
	Core
	}
}
</script>

<style>
.primary {
	min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
</style>