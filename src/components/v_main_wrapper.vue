<template>
    <div class="v_main_wrapper">
        <v-catalog />
        <v-cart v-if="CART.length" :cart_data="CART" />
    </div>
</template>

<script>

import vCatalog from './v_catalog.vue'
import vCart from './v_cart.vue'
import { mapGetters } from 'vuex'

export default {

    components: {
        vCatalog,
        vCart,
    },

    props: {},

    data() {
        return {

        }

    },
    computed: {
        ...mapGetters([
            'CART'
        ]),
    },
    methods: {},
    watch: {},


}
</script>

<style lang="scss">
.v_main_wrapper {
    max-width: 900px;
    margin: 0 auto;
    text-align: center;

}
</style>