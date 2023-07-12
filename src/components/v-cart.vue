<template>
    <div class="v-cart">
        <h1>Корзина</h1>
        <div class="v-cart-body">
            <v-cart-item
            v-for="item in cart_data"
            :key="item.id"
            :cart_item_data="item"
        />
        </div>
    </div>
</template>

<script>
import vCartItem from '@/components/v-cart-item.vue';

export default {
    name: "v-cart",
    components: {
        vCartItem,
    },
    props: {
        cart_data: {
            type: Array,
            default() {
                return []
            }
        }
    }
}
</script>

<style>
h1 {
    z-index: 20;
    margin: 30px 0  
}
.v-cart-body {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
    }
    @media (max-width: 1000px) {
        .v-cart-body {
            grid-template-columns: repeat(3, 1fr);
        }
    }
    @media (max-width: 770px) {
        .v-cart-body {
            grid-template-columns: repeat(2, 1fr);
        }
    }
    @media (max-width: 380px) {
        .v-cart-body {
            grid-template-columns: repeat(1, 1fr);
        }
    }
</style>