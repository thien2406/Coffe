<template>
  <div class="app">
    <header class="header">
      <div class="header-container">
        <h1><span class="icon">☕</span> Coffee Lan Thi</h1>
        <p>Hương vị nguyên bản - Đậm đà khó phai</p>
      </div>
    </header>

    <section class="hero">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h2>Thưởng thức ly cà phê hoàn hảo</h2>
        <p>Không gian thư giãn - Đánh thức mọi giác quan</p>
        <button class="btn-primary">Khám phá Menu</button>
      </div>
    </section>

    <section class="featured container">
      <div class="section-title">
        <h2>Thực Đơn Của Chúng Tôi</h2>
        <div class="divider"></div>
      </div>

      <div v-for="(category, index) in menuCategories" :key="index" class="menu-category">
        <h3 class="category-title">{{ category.title }}</h3>
        <div class="cards">
          <div class="card" v-for="item in category.items" :key="item.id">
            <div class="card-image-wrapper">
              <img :src="item.image" :alt="item.name" loading="lazy" />
            </div>
            <div class="card-info">
              <h3>{{ item.name }}</h3>
              <span class="price">{{ item.price }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

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

    <footer class="footer">
      <div class="container footer-content">
        <div class="footer-item">
          <h3>Coffee Lan Thi</h3>
          <p>Mang hương vị đến từng nhịp sống.</p>
        </div>
        <div class="footer-item">
          <p>📍 43 Hồ Chí Minh, Việt Nam</p>
          <p>☎ Hotline: 0859 453 545</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2026 Coffee Lan Thi. All rights reserved.</p>
      </div>
    </footer>

    <div class="floating-contact">
      <a href="https://zalo.me/0859453545" target="_blank" class="contact-icon zalo-btn" title="Chat Zalo">
        <img src="https://upload.wikimedia.org/wikipedia/commons/9/91/Icon_of_Zalo.svg" alt="Zalo" />
      </a>
      <a href="https://facebook.com" target="_blank" class="contact-icon facebook-btn" title="Chat Facebook">
        <img src="https://upload.wikimedia.org/wikipedia/commons/0/51/Facebook_f_logo_%282019%29.svg" alt="Facebook" />
      </a>
    </div>
  </div>
</template>

<script setup>
const menuCategories = [
  {
    title: "☕ Cà Phê Đậm Đà",
    items: [
      { id: 1, name: "Cà phê đen", price: "15.000đ", image: "https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=800&auto=format&fit=crop" },
      { id: 2, name: "Cà phê sữa", price: "15.000đ", image: "https://images.unsplash.com/photo-1541167760496-1628856ab772?w=800&auto=format&fit=crop" },
      { id: 3, name: "Cà phê đen Sài Gòn", price: "17.000đ", image: "https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=800&auto=format&fit=crop" },
      { id: 4, name: "Cà phê sữa Sài Gòn", price: "18.000đ - 20.000đ", image: "https://images.unsplash.com/photo-1578314675249-a6910f80cc4e?w=800&auto=format&fit=crop" },
      { id: 5, name: "Cà phê muối", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1510972527921-ce03766a1cf1?w=800&auto=format&fit=crop" },
      { id: 6, name: "Cà phê trứng", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1558562805-4bf1e2a724eb?w=800&auto=format&fit=crop" },
      { id: 7, name: "Cà phê dừa", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1594133900913-76e24169565c?w=800&auto=format&fit=crop" },
      { id: 8, name: "Cà phê sương sáo", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?w=800&auto=format&fit=crop" }
    ]
  },
  {
    title: "🥛 Bạc Xỉu Béo Ngậy",
    items: [
      { id: 9, name: "Bạc xỉu muối", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=800&auto=format&fit=crop" },
      { id: 10, name: "Bạc xỉu trứng", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1536514072410-5019a3c69182?w=800&auto=format&fit=crop" },
      { id: 11, name: "Bạc xỉu sương sáo", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=800&auto=format&fit=crop" },
      { id: 12, name: "Bạc xỉu dừa", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1541167760496-1628856ab772?w=800&auto=format&fit=crop" }
    ]
  },
  {
    title: "🍵 Trà Trái Cây & Trà Sữa",
    items: [
      { id: 13, name: "Trà chanh", price: "15.000đ", image: "https://images.unsplash.com/photo-1556679343-c7306c1976bc?w=800&auto=format&fit=crop" },
      { id: 14, name: "Trà đào", price: "20.000đ", image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=800&auto=format&fit=crop" },
      { id: 15, name: "Matcha Latte kem trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1536256263959-770b48d82b0a?w=800&auto=format&fit=crop" },
      { id: 16, name: "Khoai môn Latte kem trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1576092768241-dec231879fc3?w=800&auto=format&fit=crop" },
      { id: 17, name: "Trà sữa truyền thống kem trứng", price: "20.000đ - 25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1541658016709-82535e94bc69?w=800&auto=format&fit=crop" }
    ]
  },
  {
    title: "🍹 Nước Ép Tươi & Sinh Tố",
    items: [
      { id: 18, name: "Ép táo mix vị", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1600271886742-f049cd451bba?w=800&auto=format&fit=crop" },
      { id: 19, name: "Ép cà rốt mix cam", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1595981267035-7b04ca84a82d?w=800&auto=format&fit=crop" },
      { id: 20, name: "Nước ép chanh dây", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1573500883495-6c9b16d88d8c?w=800&auto=format&fit=crop" },
      { id: 21, name: "Nước ép cam mix", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1621506289937-a8e4df240d0b?w=800&auto=format&fit=crop" },
      { id: 22, name: "Nước ép thơm (dứa) mix", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1621263764227-849fb219f7fb?w=800&auto=format&fit=crop" },
      { id: 23, name: "Nước ép ổi", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1534432127792-bf3936932468?w=800&auto=format&fit=crop" },
      { id: 24, name: "Nước ép cà chua", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1607301401229-437a9b655314?w=800&auto=format&fit=crop" },
      { id: 25, name: "Sinh tố dâu", price: "30.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1553530666-ba11a7dd724c?w=800&auto=format&fit=crop" },
      { id: 26, name: "Sinh tố việt quất", price: "35.000đ - 40.000đ", image: "https://images.unsplash.com/photo-1604085792782-8d92f276d7d8?w=800&auto=format&fit=crop" },
      { id: 27, name: "Sinh tố xoài", price: "30.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1537640538966-79f369143f8f?w=800&auto=format&fit=crop" },
      { id: 28, name: "Sinh tố bơ", price: "35.000đ - 40.000đ", image: "https://images.unsplash.com/photo-1541532713592-79a0317b6b77?w=800&auto=format&fit=crop" }
    ]
  },
  {
    title: "🍨 Sữa Chua & Cacao, Milo Đặc Biệt",
    items: [
      { id: 29, name: "Trái cây dầm sữa chua", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1488477181946-6428a0291777?w=800&auto=format&fit=crop" },
      { id: 30, name: "Mãng cầu sữa chua", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1563805042-7684c8e9e533?w=800&auto=format&fit=crop" },
      { id: 31, name: "Ca cao muối", price: "25.000đ", image: "https://images.unsplash.com/photo-1542990253-0d0f5be5f0ed?w=800&auto=format&fit=crop" },
      { id: 32, name: "Cacao trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1600271886742-f049cd451bba?w=800&auto=format&fit=crop" },
      { id: 33, name: "Ca cao dừa", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=800&auto=format&fit=crop" },
      { id: 34, name: "Milo và Sô-cô-la trứng muối", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1544787219-7f47ccb76574?w=800&auto=format&fit=crop" }
    ]
  }
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
  background-attachment: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-overlay {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0, 0, 0, 0.5);
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
  margin-bottom: 50px;
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

/* Menu Categories */
.featured {
  padding: 60px 20px;
}

.menu-category {
  margin-bottom: 60px;
}

.category-title {
  font-size: 24px;
  color: var(--accent-color);
  margin-bottom: 25px;
  padding-left: 15px;
  border-left: 5px solid var(--primary-color);
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  gap: 25px;
}

.card {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  display: flex;
  flex-direction: column;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.1);
}

.card-image-wrapper {
  overflow: hidden;
  height: 180px;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.card:hover img {
  transform: scale(1.08);
}

.card-info {
  padding: 15px;
  text-align: center;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-info h3 {
  font-size: 16px;
  margin-bottom: 10px;
  font-family: 'Poppins', sans-serif;
  color: var(--text-main);
  font-weight: 500;
}

.price {
  color: var(--accent-color);
  font-weight: 600;
  font-size: 16px;
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

/* Floating Contact Buttons (Góc phải màn hình) */
.floating-contact {
  position: fixed;
  bottom: 30px;
  right: 30px;
  display: flex;
  flex-direction: column;
  gap: 15px;
  z-index: 999;
}

.contact-icon {
  width: 55px;
  height: 55px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
}

.contact-icon img {
  width: 32px;
  height: 32px;
  object-fit: contain;
}

.zalo-btn {
  background-color: #0068ff;
}

.facebook-btn {
  background-color: #1877f2;
}

.contact-icon:hover {
  transform: scale(1.1) translateY(-3px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
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
  
  .category-title {
    font-size: 20px;
  }

  .floating-contact {
    bottom: 20px;
    right: 20px;
    gap: 10px;
  }

  .contact-icon {
    width: 48px;
    height: 48px;
  }

  .contact-icon img {
    width: 26px;
    height: 26px;
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
    if (e.key === 'F12' || e.keyCode === 123) {
      e.preventDefault();
      return false;
    }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'I' || e.key === 'i')) {
      e.preventDefault();
      return false;
    }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'J' || e.key === 'j')) {
      e.preventDefault();
      return false;
    }
    if ((e.ctrlKey || e.metaKey) && (e.key === 'U' || e.key === 'u')) {
      e.preventDefault();
      return false;
    }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'C' || e.key === 'c')) {
      e.preventDefault();
      return false;
    }
  });
</script>