<template>
  <div class="frequently-questions-page">
    <header class="header-container">
      <router-link to="/menu" class="back-button">← voltar</router-link>
      <h1 class="title">Dúvidas Frequentes</h1>
    </header>
    <main>
      <div class="buttons-container">
        <button class="question-button" @click="goToVideo('https://youtu.be/CyE-j-0WYBo')">Como manter e cuidar o aparelho?</button>
        <button class="question-button" @click="goToVideo('https://youtu.be/gyjg8szfnes')">Posso participar de atividades físicas utilizando o aparelho?</button>
        <button class="question-button" @click="goToVideo('https://youtu.be/3dxhZznaVLs')">O aparelho corrige totalmente a perda auditiva?</button>
        <button class="question-button" @click="goToVideo('https://youtu.be/7yGD1u79AI0')">Posso usar o aparelho em um lugar barulhento?</button>
        <button class="question-button" @click="goToVideo('https://youtu.be/FtMU6QaSt50')">Como é o processo de adaptação do aparelho?</button>
        <button class="question-button" @click="goToVideo('https://youtu.be/nyf-uEhc5nc')">Como saber se preciso de um aparelho?</button>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'FrequentlyQuestionsPage',
  methods: {
    goToVideo(videoUrl) {
      this.$router.push({ name: 'FrequentlyQuestionsContent', params: { videoUrl } });
    }
  }
}
</script>

<style scoped>
.frequently-questions-page {
  text-align: center;
  padding: 10px;
}

.header-container {
  display: flex;
  justify-content: center;
  position: relative;
}

.back-button {
  position: absolute;
  top: 30px;
  left: 20px;
  font-family: 'Montserrat', sans-serif;
  font-size: 1.2rem;
  font-weight: 600;
  padding: 8px 20px;
  background-color: var(--color-background);
  color: var(--color-black)000;
  border: none;
  cursor: pointer;
  box-shadow: 5px 5px 1px -1px var(--color-text-top);
  text-align: center;
}

.title {
  color: var(--color-text-top);
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 2.5rem;
  margin: 10px auto;
  text-align: center;
  width: fit-content;
}

main {
  padding: 0px;
}

.buttons-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
  margin: 20px 0;
}

.question-button {
  background-color: var(--color-container-button);
  border: none;
  color: var(--color-black);
  font-family: 'Montserrat', sans-serif;
  font-size: 2rem;
  font-weight: 500;
  padding: 10px;
  width: 28rem;
  height: 13rem;
  cursor: pointer;
  align-items: center;
}

.exit-button {
  font-size: 1.5rem;
  font-weight: 400;
  margin-top: 20px;
  padding: 8px 20px;
  background-color: var(--color-background);
  color: var(--color-black)000;
  border: none;
  cursor: pointer;
  box-shadow: 5px 5px 1px -1px var(--color-text-top);
}

@media (max-width: 768px) {

  .title {
    margin-top: 100px;
    font-size: 2rem;
    align-content: center;
  }

  .buttons-container {
    margin-top: 40px;
    flex-direction: column;
    gap: 10px;
  }

  .question-button {
    height: 100px;
    padding: 10px 30px;
    font-size: 2rem;
    align-self: center;
  }
}

@media (max-width: 480px) {
  .question-button {
    height: 80px;
    padding: 10px 30px;
    font-size: 1.2rem;
    align-self: center;
  }

  .title {
    margin-top: 100px;
    font-size: 1.2rem;
  }

  .back-button,
  .exit-button {
    font-size: 1.2rem; 
    padding: 7px 15px; 
  }
}
</style>