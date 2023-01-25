<template>
    <h1>Catalog</h1>
    <router-link :to="{ name: 'cart', params: { cart_data: CART } }">
        <div class="v_catalog__linck_to_cart">
            Cart: {{ CART.length }}
        </div>
    </router-link>

    <div class="v_catalog">
        <v-catalog-item v-for="product in PRODUCTS" :key="product.article" :product_data="product"
            @addToCart="addToCart" />
    </div>

</template>

<script>
import vCatalogItem from './v_catalog_item.vue'
import { mapActions, mapGetters } from 'vuex'

export default {
    components: {
        vCatalogItem,
    },
    data() {
        return {

        }
    },
    computed: {
        ...mapGetters([
            'PRODUCTS',
            'CART'
        ])
    },
    methods: {
        ...mapActions([
            'GET_PRODUCTS_FROM_API',
            'ADD_TO_CART'
        ]),
        addToCart(data) {
            this.ADD_TO_CART(data)
        }
    },
    mounted() {
        this.GET_PRODUCTS_FROM_API()
    }

}
</script>

<style lang="scss">
.v_catalog {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;

    &__linck_to_cart {
        position: fixed;
        top: 10px;
        right: 10px;
        padding: $padding*2;
        border: solid 1px #ccc;
        border-radius: $radius;
        transition: all .2s linear;
        cursor: pointer;

        &:hover {
            color: #fff;
            background-color: #000;
        }

    }
}
</style>