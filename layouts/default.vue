<template>
	<NavBar />
</template>

<script>
import NavBar from '~/components/NavBar.vue';
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
    components: { NavBar }
}
</script>
