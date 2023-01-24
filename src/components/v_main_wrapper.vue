<template>
    <div class="v_main_wrapper">
        {{ title }}
    </div>

    <v-catalog />
    <v-crd />
</template>

<script>
import vCatalog from './v_catalog.vue'
import vCrd from './v_cart.vue'
export default {

    components: {
        vCatalog,
        vCrd,
    },

    props: {},

    data() {
        return {
            title: "Hello wrapp"
        }

    },
    computed: {},
    methods: {},
    watch: {},


}
</script>

<style lang="scss">
.v_main_wrapper {
    display: flex;
    justify-content: center;
    align-items: center;

}
</style>