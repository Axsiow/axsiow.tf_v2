<template>
	<NavBar />
</template>

<script>
import Card from '~/components/Card'
import NuxtLogo from '~/components/NuxtLogo.vue'
import NavBar from '../components/NavBar.vue'

export default {
	name: 'IndexPage',
	components: {
    Card,
    NavBar,
	NuxtLogo
	}
}
</script>
