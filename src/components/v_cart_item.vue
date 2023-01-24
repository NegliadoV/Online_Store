<template>
    <div class="v_cart_item">
        <img class="v_cart_item__img" :src="require('../assets/images/' + cart_item_data.image)" alt="img">
        <div class="v_cart_item__info">
            <p>{{ cart_item_data.name }}</p>
            <p>{{ cart_item_data.price }}</p>
            <p>{{ cart_item_data.article }}</p>
        </div>
        <p>Qty:</p>
        <div class="v_cart_data__quantiti">{{
            cart_item_data.quantiti
        }}</div>
        <button @click="$emit('deleteFromCart')">Delite</button>
    </div>
</template>

<script>
export default {
    name: 'v-cart-item',
    props: {
        cart_item_data: {
            type: Object,
            default() {
                return {};
            }
        }
    },
    methods: {

    },
    computed: {

    },
    mounted() {
        this.cart_item_data.quantiti = 1
    }
}
</script>

<style lang="scss">
.v_cart_item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: nowrap;
    box-shadow: 0 0 8px 0 #e0e0e0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    &__img {
        max-width: 50px;
    }
}
</style>