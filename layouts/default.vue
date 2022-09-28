<template>
	<div class="primary">
        <NavBar />
        <Footer />
    </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue';
import NuxtLogo from '~/components/NuxtLogo.vue';
import Footer from '~/components/Footer.vue';
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
    components: { NavBar, NuxtLogo, Footer }
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