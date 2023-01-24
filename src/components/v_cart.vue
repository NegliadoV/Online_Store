<template>
    <div class="v_card">
        <h1>cart</h1>
        <v-cart-item v-for="(item, index) in cart_data" :key="item.article" :cart_item_data="item"
            @deleteFromCart="deleteFromCart(index)" />
    </div>
</template>

<script>

import vCartItem from './v_cart_item.vue'
import { mapActions } from 'vuex'
export default {
    components: {
        vCartItem
    },

    props: {
        cart_data: {
            type: Array,
            default() {
                return []
            }
        }
    },
    methods: {
        ...mapActions([
            'DELITE_FROM_CART'
        ]),

        deleteFromCart(index) {
            this.DELITE_FROM_CART(index)
        },

    }
}
</script>

<style>

</style>