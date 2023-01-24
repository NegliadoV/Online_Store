<template>
    <div class="v_catalog_item">
        <img :src="imgUrl" alt="img">
        <p class="v_catalog_item__name">{{ product_data.name }}</p>
        <p class="v_catalog_item__price"> Price: {{ product_data.price }} руб.</p>
        <button class="v_catalog_item__add_btn btn" @click="addToCart">aff to cart</button>
    </div>
</template>

<script>
export default {
    props: {
        product_data: {
            default() {
                return {
                    type: Object,
                }
            }
        }
    },
    methods: {
        addToCart() {
            this.$emit('addToCart', this.product_data)
        }
    },

    computed: {
        imgUrl() {
            return require('../assets/images/' + this.product_data.image)
        }
    }

}
</script>

<style lang="scss" >
.v_catalog_item {
    flex-basis: 25%;
    box-shadow: 0 0 8px 0 #e0e0e0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    &__image {
        max-width: 100%;
    }
}
</style>