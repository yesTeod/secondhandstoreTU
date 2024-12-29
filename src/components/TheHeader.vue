<template>
  <header class="header-container">
    <div>
      <img src="/src/assets/clou.png" alt="Logo" class="header-image">
    </div>
    <nav class="nav-content">
      <div class="left-section">
        <!-- Left section placeholder for future additions -->
      </div>

      <div class="center-section">Home</div>

      <div class="right-section">
        Log in
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
  height: 70px;
  background: linear-gradient(to bottom, 
    #376EC8 3%,
    #69B7E5 10vh
  );
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
