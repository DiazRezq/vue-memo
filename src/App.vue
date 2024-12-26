<script setup>
import { ref } from "vue";
const showFrom = ref(false);
const newMemo = ref("");
const memos = ref([]);
const errorMessage = ref("");

function savedMemo() {
  if (!newMemo.value) {
    errorMessage.value = "Please enter memo";
    return;
  }
  memos.value.push({
    id: Date.now(),
    memo: newMemo.value,
    date: new Date().toLocaleString("en-GB"),
    backgroundColor: generateColor(),
  });
  newMemo.value = "";
  showFrom.value = false;
}

function removeMemo(id) {
  memos.value = memos.value.filter((memo) => memo.id !== id);
}

function generateColor() {
  return `#${Math.floor(Math.random() * 16777215).toString(16)}`;
}
</script>

<template>
  <main>
    <div class="container">
      <header>
        <h1 class="header-title">Memo</h1>
        <button @click="showFrom = true" class="header-button">+</button>
      </header>
      <div class="card-container">
        <div
          v-for="(memo, index) in memos"
          class="card"
          :key="index"
          :style="{ backgroundColor: memo.backgroundColor }"
        >
          <p class="card-text">
            {{ memo.memo }}
          </p>
          <div class="card-footer">
            <p class="card-date">{{ memo.date }}</p>
            <button @click="removeMemo(memo.id)" class="card-delete-btn">
              X
            </button>
          </div>
        </div>
      </div>
    </div>
    <div v-if="showFrom" class="form-overlay">
      <div class="form-modal">
        <button @click="showFrom = false" class="form-close-btn">
          &times;
        </button>
        <p v-if="errorMessage" class="form-error">"{{ errorMessage }}"</p>
        <textarea
          v-model="newMemo"
          name="memo"
          id="memo"
          cols="30"
          rows="10"
        ></textarea>
        <button @click="savedMemo" class="form-save-btn">Save</button>
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

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.form-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.77);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
}

.form-modal {
  display: flex;
  width: 420px;
  background-color: white;
  flex-direction: column;
  padding: 30px;
  position: relative;
  border-radius: 10px;
}

.form-save-btn {
  background-color: #495a7d;
  color: white;
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: #495a7d;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  margin-top: 15px;
  cursor: pointer;
}

.form-close-btn {
  position: absolute;
  top: 5px;
  right: 10px;
  width: 30px;
  height: 30px;
  background-color: transparent;
  border: none;
  font-size: 25px;
  cursor: pointer;
}

.form-error {
  color: red;
  margin-bottom: 10px;
}
</style>
