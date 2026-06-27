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
      </div>
    </section>

    <div class="category-sticky-bar">
      <div class="category-slider">
        <a v-for="(category, index) in menuCategories" 
           :key="index" 
           :href="'#' + category.id" 
           class="category-nav-item">
          {{ category.shortTitle }}
        </a>
      </div>
    </div>

    <section class="featured container">
      <div v-for="(category, index) in menuCategories" :key="index" :id="category.id" class="menu-category">
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
          Chúng tôi mang đến những ly cà phê chất lượng cao, tuyển chọn kỹ lưỡng
          từ những vùng nguyên liệu tốt nhất Việt Nam.
        </p>
      </div>
    </section>

    <footer class="footer">
      <div class="container footer-content">
        <div class="footer-item">
          <h3>Coffee Lan Thi</h3>
          <p>Mang hương vị đến từng nhịp sống.</p>
        </div>
        <div class="footer-item contact-info">
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
// Phân chia danh mục chi tiết, khoa học theo danh sách của bạn
const menuCategories = [
  {
    id: "cafe-truyen-thong",
    shortTitle: "Cà Phê Gốc",
    title: "☕ Cà Phê Truyền Thống",
    items: [
      { id: 1, name: "Cà phê đen", price: "15.000đ", image: "https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=500&auto=format&fit=crop" },
      { id: 2, name: "Cà phê sữa", price: "15.000đ", image: "https://images.unsplash.com/photo-1541167760496-1628856ab772?w=500&auto=format&fit=crop" },
      { id: 3, name: "Cà phê đen Sài Gòn", price: "17.000đ", image: "https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=500&auto=format&fit=crop" },
      { id: 4, name: "Cà phê sữa Sài Gòn", price: "18.000đ - 20.000đ", image: "https://images.unsplash.com/photo-1578314675249-a6910f80cc4e?w=500&auto=format&fit=crop" }
    ]
  },
  {
    id: "cafe-hien-dai",
    shortTitle: "Cà Phê Muối/Trứng",
    title: "✨ Cà Phê & Bạc Xỉu Đặc Biệt",
    items: [
      { id: 5, name: "Cà phê muối", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1510972527921-ce03766a1cf1?w=500&auto=format&fit=crop" },
      { id: 6, name: "Cà phê trứng", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1558562805-4bf1e2a724eb?w=500&auto=format&fit=crop" },
      { id: 7, name: "Cà phê dừa", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1594133900913-76e24169565c?w=500&auto=format&fit=crop" },
      { id: 8, name: "Cà phê sương sáo", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?w=500&auto=format&fit=crop" },
      { id: 9, name: "Bạc xỉu muối", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=500&auto=format&fit=crop" },
      { id: 10, name: "Bạc xỉu trứng", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1536514072410-5019a3c69182?w=500&auto=format&fit=crop" },
      { id: 11, name: "Bạc xỉu sương sáo", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=500&auto=format&fit=crop" },
      { id: 12, name: "Bạc xỉu dừa", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1541167760496-1628856ab772?w=500&auto=format&fit=crop" }
    ]
  },
  {
    id: "tra-tra-sua",
    shortTitle: "Trà & Trà Sữa",
    title: "🍵 Trà Trái Cây & Trà Sữa",
    items: [
      { id: 13, name: "Trà chanh", price: "15.000đ", image: "https://images.unsplash.com/photo-1556679343-c7306c1976bc?w=500&auto=format&fit=crop" },
      { id: 14, name: "Trà đào", price: "20.000đ", image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=500&auto=format&fit=crop" },
      { id: 15, name: "Matcha Latte kem trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1536256263959-770b48d82b0a?w=500&auto=format&fit=crop" },
      { id: 16, name: "Khoai môn Latte kem trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1576092768241-dec231879fc3?w=500&auto=format&fit=crop" },
      { id: 17, name: "Trà sữa truyền thống kem trứng", price: "20k - 25k - 30k", image: "https://images.unsplash.com/photo-1541658016709-82535e94bc69?w=500&auto=format&fit=crop" }
    ]
  },
  {
    id: "nuoc-ep-sinh-to",
    shortTitle: "Ép & Sinh Tố",
    title: "🍹 Nước Ép Nguyên Chất & Sinh Tố",
    items: [
      { id: 18, name: "Nước ép táo mix vị", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1600271886742-f049cd451bba?w=500&auto=format&fit=crop" },
      { id: 19, name: "Nước ép cà rốt mix cam", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1595981267035-7b04ca84a82d?w=500&auto=format&fit=crop" },
      { id: 20, name: "Nước ép chanh dây", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1573500883495-6c9b16d88d8c?w=500&auto=format&fit=crop" },
      { id: 21, name: "Nước ép cam mix", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1621506289937-a8e4df240d0b?w=500&auto=format&fit=crop" },
      { id: 22, name: "Nước ép thơm (dứa) mix", price: "25.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1621263764227-849fb219f7fb?w=500&auto=format&fit=crop" },
      { id: 23, name: "Nước ép ổi", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1534432127792-bf3936932468?w=500&auto=format&fit=crop" },
      { id: 24, name: "Nước ép cà chua", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1607301401229-437a9b655314?w=500&auto=format&fit=crop" },
      { id: 25, name: "Sinh tố dâu", price: "30.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1553530666-ba11a7dd724c?w=500&auto=format&fit=crop" },
      { id: 26, name: "Sinh tố việt quất", price: "35.000đ - 40.000đ", image: "https://images.unsplash.com/photo-1604085792782-8d92f276d7d8?w=500&auto=format&fit=crop" },
      { id: 27, name: "Sinh tố xoài", price: "30.000đ - 35.000đ", image: "https://images.unsplash.com/photo-1537640538966-79f369143f8f?w=500&auto=format&fit=crop" },
      { id: 28, name: "Sinh tố bơ", price: "35.000đ - 40.000đ", image: "https://images.unsplash.com/photo-1541532713592-79a0317b6b77?w=500&auto=format&fit=crop" }
    ]
  },
  {
    id: "sua-chua-khac",
    shortTitle: "Sữa Chua & CaCao",
    title: "🍨 Sữa Chua Dầm & Cacao, Milo Kem Trứng",
    items: [
      { id: 29, name: "Trái cây dầm sữa chua", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1488477181946-6428a0291777?w=500&auto=format&fit=crop" },
      { id: 30, name: "Mãng cầu sữa chua", price: "20.000đ - 25.000đ", image: "https://images.unsplash.com/photo-1563805042-7684c8e9e533?w=500&auto=format&fit=crop" },
      { id: 31, name: "Ca cao muối", price: "25.000đ", image: "https://images.unsplash.com/photo-1542990253-0d0f5be5f0ed?w=500&auto=format&fit=crop" },
      { id: 32, name: "Cacao trứng", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1600271886742-f049cd451bba?w=500&auto=format&fit=crop" },
      { id: 33, name: "Ca cao dừa", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?w=500&auto=format&fit=crop" },
      { id: 34, name: "Milo & Sô-cô-la trứng muối", price: "25.000đ - 30.000đ", image: "https://images.unsplash.com/photo-1544787219-7f47ccb76574?w=500&auto=format&fit=crop" }
    ]
  }
];
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Poppins:wght@300;400;500;600&display=swap');

:root {
  --primary-color: #3e2723; 
  --accent-color: #d84315; 
  --bg-color: #fcf9f2; 
  --text-main: #2b2b2b;
  --text-muted: #777777;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth; /* Tạo hiệu ứng cuộn mượt khi bấm danh mục */
}

body {
  background-color: var(--bg-color);
  font-family: 'Poppins', sans-serif;
  color: var(--text-main);
  line-height: 1.5;
  -webkit-tap-highlight-color: transparent; /* Tối ưu trải nghiệm chạm trên điện thoại */
}

h1, h2, h3 {
  font-family: 'Playfair Display', serif;
  color: var(--primary-color);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 12px; /* Thu hẹp padding một chút cho màn hình nhỏ */
}

/* Header */
.header {
  background-color: white;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
  padding: 15px 0;
  text-align: center;
}

.header h1 {
  font-size: 22px;
  margin-bottom: 2px;
}

.header p {
  font-size: 12px;
  color: var(--text-muted);
}

/* Hero Section cho Mobile */
.hero {
  position: relative;
  height: 200px; /* Hạ thấp chiều cao tránh chiếm diện tích hiển thị món ăn */
  background: url("https://images.unsplash.com/photo-1442512595331-e89e73853f31?w=1000&auto=format&fit=crop");
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-overlay {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0, 0, 0, 0.45);
}

.hero-content {
  position: relative;
  color: white;
  text-align: center;
  padding: 0 15px;
  z-index: 1;
}

.hero-content h2 {
  color: white;
  font-size: 24px;
  margin-bottom: 5px;
  text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
}

.hero-content p {
  font-size: 13px;
  font-weight: 300;
}

/* STICKY CATEGORY SLIDER (Thanh trượt danh mục thông minh) */
.category-sticky-bar {
  position: sticky;
  top: 0;
  background-color: white;
  z-index: 99;
  box-shadow: 0 4px 10px rgba(0,0,0,0.06);
  border-bottom: 1px solid #eeeeee;
}

.category-slider {
  display: flex;
  overflow-x: auto;
  white-space: nowrap;
  padding: 12px 8px;
  gap: 10px;
  scroll-磨损: smooth;
}

/* Ẩn thanh cuộn xấu xí trên các trình duyệt di động để giao diện mượt hơn */
.category-slider::-webkit-scrollbar {
  display: none;
}
.category-slider {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

.category-nav-item {
  display: inline-block;
  padding: 8px 16px;
  background-color: #f5f5f5;
  color: var(--text-main);
  text-decoration: none;
  font-size: 13px;
  font-weight: 500;
  border-radius: 20px;
  transition: all 0.2s ease;
}

.category-nav-item:hover, .category-nav-item:active {
  background-color: var(--primary-color);
  color: white;
}

/* Menu Layout */
.featured {
  padding: 30px 12px;
}

.menu-category {
  margin-bottom: 40px;
  scroll-margin-top: 70px; /* Khoảng cách dừng khi nhấn nhảy mục tránh bị đè dưới thanh sticky */
}

.category-title {
  font-size: 18px;
  color: var(--primary-color);
  margin-bottom: 18px;
  padding-left: 10px;
  border-left: 4px solid var(--accent-color);
}

/* Cấu trúc GRID chuẩn Mobile: 2 cột */
.cards {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* Ép hiển thị đúng 2 cột trên màn hình nhỏ */
  gap: 12px;
}

.card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 3px 8px rgba(0,0,0,0.04);
  display: flex;
  flex-direction: column;
}

.card-image-wrapper {
  overflow: hidden;
  aspect-ratio: 1 / 1; /* Biến ảnh thành hình vuông đều đặn rất đẹp */
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-info {
  padding: 10px;
  text-align: center;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-info h3 {
  font-size: 13px;
  margin-bottom: 6px;
  font-family: 'Poppins', sans-serif;
  color: var(--text-main);
  font-weight: 500;
  display: -webkit-box;
  -webkit-line-clamp: 2; /* Giới hạn tối đa 2 dòng tên món, không sợ lệch khung */
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.price {
  color: var(--accent-color);
  font-weight: 600;
  font-size: 13px;
}

/* About */
.about {
  background-color: white;
  padding: 40px 15px;
  text-align: center;
}

.about h2 { font-size: 20px; }
.divider {
  width: 40px;
  height: 2px;
  background-color: var(--accent-color);
  margin: 10px auto;
}
.about p {
  font-size: 14px;
  color: var(--text-muted);
  max-width: 500px;
  margin: 0 auto;
}

/* Footer */
.footer {
  background-color: var(--primary-color);
  color: rgba(255, 255, 255, 0.75);
  padding: 40px 15px 20px;
  text-align: center;
}

.footer-content {
  display: flex;
  flex-direction: column; /* Xếp dọc toàn bộ trên điện thoại */
  gap: 20px;
  border-bottom: 1px solid rgba(255,255,255,0.08);
  padding-bottom: 25px;
  margin-bottom: 20px;
}

.footer-item h3 {
  color: white;
  font-size: 18px;
  margin-bottom: 10px;
}

.footer-item p {
  font-size: 13px;
  margin-bottom: 5px;
}

.footer-bottom {
  font-size: 11px;
}

/* Floating Contact (Tối ưu nhỏ gọn vừa tay chạm) */
.floating-contact {
  position: fixed;
  bottom: 20px;
  right: 15px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  z-index: 999;
}

.contact-icon {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.18);
  transition: transform 0.2s ease;
}

.contact-icon img {
  width: 26px;
  height: 26px;
}

.zalo-btn { background-color: #0068ff; }
.facebook-btn { background-color: #1877f2; }

.contact-icon:active {
  transform: scale(0.9); /* Hiệu ứng lún nút khi chạm tay trên Mobile */
}

/* CẤU HÌNH PHỤ TRÊN MÀN HÌNH LỚN (MÁY TÍNH) - Giúp web mở máy tính vẫn đẹp */
@media (min-width: 768px) {
  .header h1 { font-size: 28px; }
  .hero { height: 320px; }
  .hero-content h2 { font-size: 38px; }
  .cards { grid-template-columns: repeat(4, 1fr); gap: 20px; } /* Mở rộng 4 cột khi xem máy tính */
  .card-info h3 { font-size: 15px; }
  .price { font-size: 15px; }
  .footer-content { flex-direction: row; justify-content: space-between; text-align: left; }
  .category-slider { justify-content: center; overflow: visible; }
}
</style>

<script>
  // Đoạn script bảo mật chống F12, sao chép của bạn giữ nguyên
  document.addEventListener('contextmenu', function(e) { e.preventDefault(); });
  document.addEventListener('keydown', function(e) {
    if (e.key === 'F12' || e.keyCode === 123) { e.preventDefault(); return false; }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'I' || e.key === 'i')) { e.preventDefault(); return false; }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'J' || e.key === 'j')) { e.preventDefault(); return false; }
    if ((e.ctrlKey || e.metaKey) && (e.key === 'U' || e.key === 'u')) { e.preventDefault(); return false; }
    if ((e.ctrlKey || e.metaKey) && (e.shiftKey || e.altKey) && (e.key === 'C' || e.key === 'c')) { e.preventDefault(); return false; }
  });
</script>