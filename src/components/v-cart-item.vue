<template>
    <div class="v-cart-item">
        <img class="v-cart-item__img" :src="require ('../assets/images/' + cart_item_data.image)" alt="img">
        <div class="v-cart-item-info">
            <p>{{cart_item_data.name}}</p>
            <p>{{cart_item_data.price}}</p>
            <p>{{cart_item_data.article}}</p>
        </div>
        <div 
            class="v-cart-item_quantity"
        >
        <p>Qty:</p>
        <span class="quantity__btn" @click="decrementItem">-</span>
        {{cart_item_data.quantity}}
        <span class="quantity__btn" @click="incrementItem">+</span>
        </div>
        <button class="btn" v-on:click="deleteFromCart">Delete</button>
    </div>
</template>


<script>


export default {
    name: "v-cart-item",
    props: {
        cart_item_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return {}
    },
    computed: {},
    methods: {
        deleteFromCart() {
            this.$emit('deleteFromCart')
        },
        decrementItem() {
            this.$emit('decrement')
        }, 
        incrementItem() {
            this.$emit('increment')
        }
    },
    mounted() {
        this.$set(this.cart_item_data, 'quantity', 1)
    }
}
</script>


<style lang="scss">
    .v-cart-item {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: $padding*2;
        margin-bottom: $margin*2;

        &__img {
            max-width: 50px;
        }
        .quantity__btn {
            cursor: pointer;
        }
    }
</style>