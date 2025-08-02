<template>
  <div class="home">
    <div class="home-card">
      <h1>Welcome to Stimulastik</h1>
      <p>Discover activities, inspiration, and more for your journey.</p>
    </div>
  </div>
</template>

<style scoped>
.home {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #f8fafc 0%, #e0e7ff 100%);
  font-family: 'Segoe UI', 'Roboto', Arial, sans-serif;
}

.home-card {
  background: #fff;
  padding: 3rem 2.5rem;
  border-radius: 1.5rem;
  box-shadow: 0 8px 32px rgba(60, 72, 100, 0.15);
  text-align: center;
  max-width: 420px;
  width: 100%;
  transition: box-shadow 0.2s;
}

.home-card:hover {
  box-shadow: 0 12px 40px rgba(60, 72, 100, 0.22);
}

.home-card h1 {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: #3730a3;
  letter-spacing: -1px;
}

.home-card p {
  font-size: 1.15rem;
  color: #64748b;
}
</style>
