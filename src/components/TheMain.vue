<template>
  <div class="main-content">
    <div class="content-container">
      <div class="square left-square"></div>
      <div class="text-space">
        AAAAAAAAAAAAAA AAAAAAAAAAAAAA AAAAAAAAAAAAAA AAAAAAAAAAAAAA AAAAAAAAAAAAAA AAAAAAAAAAAAAA
        AAAAAAAAAAAAAA AAAAAAAAAAAAAA
      </div>
      <div class="square right-square"></div>
    </div>
  </div>
</template>

<style scoped>
.main-content {
  min-height: calc(100vh - 60px);
  margin-top: 60px; /* Match header height */
  background: #69b7e5;
  width: 100%;
  display: flex;
  justify-content: center;
}

.content-container {
  width: 66.67%; /* 2/3 of the window width */
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
}

.square {
  width: 200px;
  height: 200px;
  background-color: white;
  border-radius: 4px;
}

.text-space {
  flex: 1;
  margin: 0 20px;
  min-height: 200px;
}

@media (max-width: 768px) {
  .main-content {
    margin-top: 50px; /* Match mobile header height */
  }

  .content-container {
    flex-direction: column;
    width: 90%;
  }

  .square {
    margin: 10px 0;
  }

  .text-space {
    margin: 10px 0;
  }
}
</style>
