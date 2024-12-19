<template>
  <header class="header-container">
    <nav class="nav-content">
      <div class="left-section">
        <!-- Left section placeholder for future additions -->
      </div>

      <div class="center-section">Home</div>

      <div class="right-section">
        <img src="/src/assets/Compass.webp" alt="Logo" class="header-image" />
      </div>
    </nav>
  </header>
</template>

<style scoped>
.header-container {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
  background: linear-gradient(to bottom, #376ec8, #69b7e5);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.nav-content {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.left-section {
  padding-left: 20px;
}

.right-section {
  padding-right: 20px;
}

.center-section {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

.header-image {
  height: 40px;
  width: auto;
  object-fit: contain;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .header-container {
    height: 50px;
  }

  .left-section {
    padding-left: 10px;
  }

  .right-section {
    padding-right: 10px;
  }

  .header-image {
    height: 30px;
  }
}
</style>
