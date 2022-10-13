<template>
	<div class="primary">
        <NavBar />
		<Core />
		<parcours />
        <Footer />
    </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue';
import NuxtLogo from '~/components/NuxtLogo.vue';
import Footer from '~/components/Footer.vue';
import Card from '~/components/Card.vue';
export default {
    name: "DefaultLayout",
    data() {
        return {
            items: [
                {
                	title: "Home",
                    icon: "home",
                    to: { name: "index" }
                },
                {
                    title: "Inspire",
                    icon: "lightbulb",
                    to: { name: "inspire" }
                }
            ]
        };
    },
    components: { NavBar, NuxtLogo, Footer, Card }
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