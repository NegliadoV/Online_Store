<template>
    <h1>Catalog</h1>
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
            'PRODUCTS'
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
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
}
</style>