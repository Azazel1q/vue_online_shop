<template>
    <div class="v-cart">
        <h1>Корзина</h1>
        <v-cart-item/>
    </div>
</template>

<script>
import vCartItem from './v-cart-item.vue';

export default {
    name: "v-cart",
    components: {
        vCartItem,
    }
}
</script>

<style>

</style>