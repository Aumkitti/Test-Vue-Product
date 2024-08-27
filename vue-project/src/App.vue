<script setup>
import { defineProps } from "vue";

const products = [
  {
    id: 1,
    image: "/images/image_1.jpg",
    image2: "/images/slide1.png",
    title: "กระโปรงนักศึกษา ทรงเอยาว 16-18",
    price: 99.0,
    sold: 1100,
    rating: 353,
    location: "กรุงเทพมหานคร",
  },
  {
    id: 2,
    image: "/images/image_2.jpg",
    image2: "/images/slide2.png",
    title: "กระโปรงนักศึกษา ทรงเอผ่าหน้า ผ้าฮานาโกะ ความยาว 14 - 15 - 18 เอว 23 - 34",
    price: 100.0,
    sold: 143,
    rating: 31,
    location: "กรุงเทพมหานคร",
  },
  {
    id: 3,
    image: "/images/image_3.jpg",
    image2: "/images/slide3.png",
    title: "กระโปรงนักศึกษา ทรงเอยาว 20 22 24",
    price: 129.0,
    sold: 435,
    rating: 174,
    location: "กรุงเทพมหานคร",
  },
  {
    id: 4,
    image: "/images/image_4.jpg",
    image2: "/images/slide4.png",
    title: "กระโปรงนักศึกษา ทรงเอ (ผ่าหลัง)",
    price: 99.0,
    sold: 932,
    rating: 465,
    location: "ปทุมธานี",
  },
];
</script>

<template>
  <div class="product-listing">
    <div class="grid grid-cols-4 gap-4">
      <div v-for="product in products" :key="product.id" class="product-card">
        <img :src="product.image" alt="Product Image" class="product-image" />
        <div class="small-image-container">
          <img :src="product.image2" alt="Product Image" class="small-image" />
        </div>
        <div class="product-details">
          <h2 class="product-title">{{ product.title }}</h2>
          <p class="product-price">฿{{ product.price }}</p>
          <div class="product-info-row">
            <p class="product-sold">{{ product.sold }} ชิ้น</p>
            <div class="product-rating">
              <span>⭐⭐⭐⭐⭐</span> ({{ product.rating }})
            </div>
            <p class="product-location">{{ product.location }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.product-listing {
  padding: 20px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
}

.product-card {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
  padding: 20px;
  text-align: center;
  flex: 0 0 auto;
  width: 300px;
  height: 550px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
}

.product-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 8px;
}

.product-details {
  margin-top: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.product-price {
  font-size: 18px;
  color: #f58a14;
  margin-bottom: 10px;
}

.product-info-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 5px;
  width: 100%;
  font-size: 15px;
}

.product-title {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 8px;
}

.product-sold,
.product-rating {
  font-size: 12px;
}

.product-location {
  font-size: 13px;
  color: #777;
}
</style>
