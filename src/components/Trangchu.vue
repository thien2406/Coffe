<template>
  <div class="app">
    <!-- Header -->
    <header class="header">
      <h1>☕ Coffee Lan Thi</h1>
      <p>Hương vị cà phê nguyên chất</p>
    </header>

    <!-- Banner -->
    <section class="hero">
      <div class="hero-content">
        <h2>Thưởng thức ly cà phê hoàn hảo</h2>
        <p>Không gian thư giãn - Hương vị đậm đà</p>
        <button>Xem Menu</button>
      </div>
    </section>

    <!-- Menu nổi bật -->
    <section class="featured">
      <h2>Thức uống nổi bật</h2>

      <div class="cards">
        <div class="card" v-for="item in drinks" :key="item.id">
          <img :src="item.image" :alt="item.name" />
          <h3>{{ item.name }}</h3>
          <p>{{ item.price }}</p>
        </div>
      </div>
    </section>

    <!-- Giới thiệu -->
    <section class="about">
      <h2>Về chúng tôi</h2>
      <p>
        Chúng tôi mang đến những ly cà phê chất lượng cao được tuyển chọn
        từ những vùng nguyên liệu tốt nhất Việt Nam.
      </p>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>📍 Địa chỉ: 43 Ho Chi Minh</p>
      <p>☎ 0123 456 789</p>
    </footer>
  </div>
</template>

<script setup>
const drinks = [
  {
    id: 1,
    name: "Cà phê sữa",
    price: "25.000đ",
    image:
      "https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=500",
  },
  {
    id: 2,
    name: "Bạc xỉu",
    price: "30.000đ",
    image:
      "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=500",
  },
  {
    id: 3,
    name: "Trà đào",
    price: "35.000đ",
    image:
      "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=500",
  },
];
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #f5f5f5;
  font-family: Arial, sans-serif;
}

.header {
  background: #4e342e;
  color: white;
  text-align: center;
  padding: 20px;
}

.hero {
  height: 300px;
  background: linear-gradient(rgba(0,0,0,.5), rgba(0,0,0,.5)),
    url("https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=1200");
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-content {
  color: white;
  text-align: center;
}

.hero button {
  margin-top: 15px;
  padding: 10px 20px;
  border: none;
  background: #ff9800;
  color: white;
  border-radius: 8px;
  cursor: pointer;
}

.featured {
  padding: 30px 15px;
}

.featured h2 {
  text-align: center;
  margin-bottom: 20px;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 15px;
}

.card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 3px 10px rgba(0,0,0,.1);
}

.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.card h3,
.card p {
  padding: 10px;
}

.about {
  padding: 30px 20px;
  text-align: center;
  background: white;
}

.footer {
  background: #4e342e;
  color: white;
  text-align: center;
  padding: 20px;
}

/* Mobile */
@media (max-width: 768px) {
  .hero {
    height: 250px;
  }

  .hero-content h2 {
    font-size: 24px;
  }
}
</style>