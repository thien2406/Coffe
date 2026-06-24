<template>
  <div class="app">
    <!-- Header -->
    <header class="header">
      <div class="header-container">
        <h1><span class="icon">☕</span> Coffee Lan Thi</h1>
        <p>Hương vị nguyên bản - Đậm đà khó phai</p>
      </div>
    </header>

    <!-- Banner -->
    <section class="hero">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h2>Thưởng thức ly cà phê hoàn hảo</h2>
        <p>Không gian thư giãn - Đánh thức mọi giác quan</p>
        <button class="btn-primary">Khám phá Menu</button>
      </div>
    </section>

    <!-- Menu nổi bật -->
    <section class="featured container">
      <div class="section-title">
        <h2>Thức uống nổi bật</h2>
        <div class="divider"></div>
      </div>

      <div class="cards">
        <div class="card" v-for="item in drinks" :key="item.id">
          <div class="card-image-wrapper">
            <img :src="item.image" :alt="item.name" />
          </div>
          <div class="card-info">
            <h3>{{ item.name }}</h3>
            <span class="price">{{ item.price }}</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Giới thiệu -->
    <section class="about">
      <div class="container about-content">
        <h2>Về chúng tôi</h2>
        <div class="divider"></div>
        <p>
          Chúng tôi mang đến những ly cà phê chất lượng cao, được tuyển chọn kỹ lưỡng
          từ những vùng nguyên liệu tốt nhất Việt Nam. Mỗi tách cà phê là một câu chuyện
          về sự tận tâm và đam mê.
        </p>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container footer-content">
        <div class="footer-item">
          <h3>Coffee Lan Thi</h3>
          <p>Mang hương vị đến từng nhịp sống.</p>
        </div>
        <div class="footer-item">
          <p>📍 43 Hồ Chí Minh, Việt Nam</p>
          <p>☎ Hotline: 0123 456 789</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2026 Coffee Lan Thi. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
const drinks = [
  {
    id: 1,
    name: "Cà phê sữa đá",
    price: "25.000đ",
    image: "https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=800&auto=format&fit=crop",
  },
  {
    id: 2,
    name: "Bạc xỉu",
    price: "30.000đ",
    image: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=800&auto=format&fit=crop",
  },
  {
    id: 3,
    name: "Trà đào cam sả",
    price: "35.000đ",
    image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=800&auto=format&fit=crop",
  },
];
</script>

<style>
/* Import Fonts: Playfair cho tiêu đề, Poppins cho văn bản */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,600;0,700;1,600&family=Poppins:wght@300;400;500;600&display=swap');

:root {
  --primary-color: #3e2723; /* Nâu cà phê đậm */
  --accent-color: #d84315; /* Cam cháy */
  --bg-color: #fcf9f2; /* Màu kem nhạt */
  --text-main: #333333;
  --text-muted: #666666;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: var(--bg-color);
  font-family: 'Poppins', sans-serif;
  color: var(--text-main);
  line-height: 1.6;
}

h1, h2, h3 {
  font-family: 'Playfair Display', serif;
  color: var(--primary-color);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header */
.header {
  background-color: white;
  box-shadow: 0 2px 10px rgba(0,0,0,0.05);
  padding: 20px 0;
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-container {
  text-align: center;
}

.header h1 {
  font-size: 28px;
  margin-bottom: 5px;
}

.header p {
  font-size: 14px;
  color: var(--text-muted);
  font-weight: 300;
}

/* Hero Section */
.hero {
  position: relative;
  height: 450px;
  background: url("https://images.unsplash.com/photo-1442512595331-e89e73853f31?w=1600&auto=format&fit=crop");
  background-size: cover;
  background-position: center;
  background-attachment: fixed; /* Hiệu ứng Parallax nhẹ */
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-overlay {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0, 0, 0, 0.5); /* Phủ mờ để chữ nổi bật */
}

.hero-content {
  position: relative;
  color: white;
  text-align: center;
  z-index: 1;
  padding: 0 20px;
}

.hero-content h2 {
  color: white;
  font-size: 42px;
  margin-bottom: 10px;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.hero-content p {
  font-size: 18px;
  margin-bottom: 25px;
  font-weight: 300;
}

.btn-primary {
  padding: 12px 30px;
  border: none;
  background-color: var(--accent-color);
  color: white;
  font-family: 'Poppins', sans-serif;
  font-size: 16px;
  font-weight: 500;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(216, 67, 21, 0.3);
}

.btn-primary:hover {
  background-color: #bf360c;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(216, 67, 21, 0.4);
}

/* Titles */
.section-title {
  text-align: center;
  margin-bottom: 40px;
}

.section-title h2 {
  font-size: 32px;
}

.divider {
  width: 60px;
  height: 3px;
  background-color: var(--accent-color);
  margin: 15px auto 0;
  border-radius: 2px;
}

/* Featured Menu */
.featured {
  padding: 80px 20px;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.card {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.1);
}

.card-image-wrapper {
  overflow: hidden;
}

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.card:hover img {
  transform: scale(1.05); /* Zoom nhẹ ảnh khi hover */
}

.card-info {
  padding: 20px;
  text-align: center;
}

.card-info h3 {
  font-size: 20px;
  margin-bottom: 10px;
}

.price {
  color: var(--accent-color);
  font-weight: 600;
  font-size: 18px;
}

/* About Section */
.about {
  background-color: white;
  padding: 80px 20px;
}

.about-content p {
  max-width: 700px;
  margin: 20px auto 0;
  font-size: 16px;
  color: var(--text-muted);
  text-align: center;
}

/* Footer */
.footer {
  background-color: var(--primary-color);
  color: rgba(255, 255, 255, 0.8);
  padding: 60px 20px 20px;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 30px;
  margin-bottom: 40px;
  border-bottom: 1px solid rgba(255,255,255,0.1);
  padding-bottom: 30px;
}

.footer-item h3 {
  color: white;
  margin-bottom: 15px;
}

.footer-item p {
  margin-bottom: 8px;
  font-size: 14px;
}

.footer-bottom {
  text-align: center;
  font-size: 13px;
}

/* Responsive cho Mobile */
@media (max-width: 768px) {
  .hero {
    height: 350px;
  }
  
  .hero-content h2 {
    font-size: 32px;
  }

  .footer-content {
    flex-direction: column;
    text-align: center;
  }
}
</style>
<script>
  // Chặn menu chuột phải
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });

  // Chặn các phím tắt DevTools (Bao gồm cả Windows và macOS)
  document.addEventListener('keydown', function(e) {
    // Chặn F12
    if (e.key === 'F12' || e.keyCode === 123) {
      e.preventDefault();
      return false;
    }
    
    // Chặn Ctrl+Shift+I (Windows) hoặc Cmd+Option+I (Mac)
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'I' || e.key === 'i')) {
      e.preventDefault();
      return false;
    }

    // Chặn Ctrl+Shift+J (Windows) hoặc Cmd+Option+J (Mac)
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'J' || e.key === 'j')) {
      e.preventDefault();
      return false;
    }

    // Chặn Ctrl+U (Windows) hoặc Cmd+Option+U (Mac) - Xem mã nguồn
    if ((e.ctrlKey || e.metaKey) && (e.key === 'U' || e.key === 'u')) {
      e.preventDefault();
      return false;
    }

    // Chặn Ctrl+Shift+C (Windows) hoặc Cmd+Option+C (Mac) - Inspect Element
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'C' || e.key === 'c')) {
      e.preventDefault();
      return false;
    }
  });
</script>