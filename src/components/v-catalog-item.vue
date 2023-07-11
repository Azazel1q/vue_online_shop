<template>
    <div class="v-catalog-item card">
        <img :src="product_data.img" class="card__img" alt="card-horizontal-image">
        <div class="card__content">
          <p class="card__title">Название: {{ product_data.name }}</p>
          <p class="card__description">Стоимость: {{ product_data.price }}</p>
          <button class="btn-primary" @click="addToCart">Добавить в корзину</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
          product_data: {
            type: Object,
            default() {
              return {}
            }
          },
        },
        methods: {
          addToCart() {
            this.$emit('addToCart', this.product_data)
          }
        }
    }
</script>

<style>
.v-catalog-item {
  background: #d6d6d6;
  box-shadow:  20px 20px 41px #b6b6b6,
       -20px -20px 41px #f6f6f6;
  border-radius: 20px;
  overflow: hidden;
}
.card {
  position: relative;
  height: 200px;
  background-color: #f2f2f2;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  perspective: 1000px;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card__img {
  width: auto;
  height: 100%;
}

.card:hover {
  transform: scale(1.05);
  background: linear-gradient(145deg, #e5e5e5, #c1c1c1);
box-shadow:  20px 20px 14px #b6b6b6,
             -20px -20px 14px #f6f6f6;
}

.card__content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 20px;
  box-sizing: border-box;
  background-color: #f2f2f2;
  transform: rotateX(-90deg);
  transform-origin: bottom;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.card:hover .card__content {
  transform: rotateX(0deg);
}

.card__title {
  margin: 0;
  font-size: 24px;
  color: #333;
  font-weight: 700;
}

.card:hover svg {
  scale: 0;
}

.card__description {
  margin: 10px 0 0;
  font-size: 14px;
  color: #777;
  line-height: 1.4;
}

</style>