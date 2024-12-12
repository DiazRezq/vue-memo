<template>
  <main>
    <div class="container">
      <header>
        <h1 class="header-title">Memo</h1>
        <button class="header-button">+</button>
      </header>
      <div class="card-container">
        <div class="card">
          <p class="card-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci
            reiciendis dignissimos velit, esse impedit neque aliquid sed hic
            dicta quia? Expedita consequatur exercitationem quo beatae
            repellendus adipisci, nam maiores porro?
          </p>
          <p class="card-date">19/10/2024</p>
        </div>
        <div class="card">
          <p class="card-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci
            reiciendis dignissimos velit, esse impedit neque aliquid sed hic
            dicta quia? Expedita consequatur exercitationem quo beatae
            repellendus adipisci, nam maiores porro?
          </p>
          <p class="card-date">19/10/2024</p>
        </div>
        <div class="card">
          <p class="card-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci
            reiciendis dignissimos velit, esse impedit neque aliquid sed hic
            dicta quia? Expedita consequatur exercitationem quo beatae
            repellendus adipisci, nam maiores porro?
          </p>
          <p class="card-date">19/10/2024</p>
        </div>
        <div class="card">
          <p class="card-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci
            reiciendis dignissimos velit, esse impedit neque aliquid sed hic
            dicta quia? Expedita consequatur exercitationem quo beatae
            repellendus adipisci, nam maiores porro?
          </p>
          <p class="card-date">19/10/2024</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  width: 100vw;
}

.container {
  max-width: 900px;
  padding: 10px;
  margin: 0 auto;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header-title {
  font-size: 48px;
  font-weight: bold;
  margin-bottom: 20px;
  color: #495a7d;
}

.header-button {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  padding: 10px;
  cursor: pointer;
  border-radius: 100%;
  background-color: #495a7d;
  color: white;
}

.card {
  display: flex;
  width: 225px;
  height: 225px;
  padding: 10px;
  background-color: aquamarine;
  margin-bottom: 20px;
  flex-direction: column;
  justify-content: space-between;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
