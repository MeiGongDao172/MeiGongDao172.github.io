---
layout: default
title: 画廊
---

<style>
  /* 画廊网格布局 */
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    margin-top: 20px;
  }
  
  /* 图片卡片 */
  .gallery-card {
    cursor: pointer;
    transition: transform 0.2s;
  }
  
  .gallery-card:hover {
    transform: scale(1.02);
  }
  
  .gallery-card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    display: block;
  }
  
  .gallery-card .card-title {
    text-align: center;
    margin-top: 8px;
    font-size: 14px;
  }
  
  /* 灯箱遮罩层 */
  .lightbox {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
    backdrop-filter: blur(8px);
    z-index: 1000;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }
  
  /* 灯箱内大图 */
  .lightbox img {
    max-width: 90%;
    max-height: 90%;
    object-fit: contain;
    box-shadow: 0 0 30px rgba(0,0,0,0.5);
  }
  
  /* 关闭按钮 */
  .close-btn {
    position: absolute;
    top: 20px;
    right: 40px;
    color: white;
    font-size: 40px;
    font-weight: bold;
    cursor: pointer;
    z-index: 1001;
  }
  
  .close-btn:hover {
    color: #ccc;
  }
</style>

# 画廊

这里存放一些我的作品截图。

<div class="gallery-grid">
  <!-- 图片 1 -->
  <div class="gallery-card" onclick="openLightbox('/images/爱你老己明天见.jpg')">
    <img src="/images/爱你老己明天见.jpg" alt="2026.4.22">
    <div class="card-title">2026.4.22</div>
  </div>
  
  <!-- 图片 2（占位符，可替换） -->
  <div class="gallery-card" onclick="openLightbox('/images/placeholder2.jpg')">
    <img src="/images/placeholder2.jpg" alt="图片标题2" onerror="this.src='https://picsum.photos/200/150?random=2'">
    <div class="card-title">图片标题 2</div>
  </div>
  
  <!-- 图片 3（占位符，可替换） -->
  <div class="gallery-card" onclick="openLightbox('/images/placeholder3.jpg')">
    <img src="/images/placeholder3.jpg" alt="图片标题3" onerror="this.src='https://picsum.photos/200/150?random=3'">
    <div class="card-title">图片标题 3</div>
  </div>
  
  <!-- 图片 4（占位符，可替换） -->
  <div class="gallery-card" onclick="openLightbox('/images/placeholder4.jpg')">
    <img src="/images/placeholder4.jpg" alt="图片标题4" onerror="this.src='https://picsum.photos/200/150?random=4'">
    <div class="card-title">图片标题 4</div>
  </div>
</div>

<!-- 灯箱 -->
<div id="lightbox" class="lightbox" onclick="closeLightbox()">
  <span class="close-btn">&times;</span>
  <img id="lightbox-img" src="">
</div>

<script>
  function openLightbox(imageUrl) {
    var lightbox = document.getElementById('lightbox');
    var lightboxImg = document.getElementById('lightbox-img');
    lightbox.style.display = 'flex';
    lightboxImg.src = imageUrl;
  }
  
  function closeLightbox() {
    var lightbox = document.getElementById('lightbox');
    lightbox.style.display = 'none';
  }
</script>
