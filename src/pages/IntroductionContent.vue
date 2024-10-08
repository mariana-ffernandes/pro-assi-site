<template>
    <div class="conteudo-introducao-page">
      <header class="header-container">
        <router-link to="/introduction" class="back-button">← voltar</router-link> 
        <h1 class="title">Módulo {{ moduleId }}</h1>
      </header>
      <main class="main-container">
        <div class="video-container">
          <div v-if="moduleId == 1">
            <iframe
              class="video"
              :src="getYoutubeEmbedUrl('https://youtu.be/cRpoTeF3wIA')"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen>
            </iframe>
          </div>
          <div v-else-if="moduleId == 2">
            <h2 class="module-title">Módulo 2: Função do Aparelho</h2>
            <iframe
              class="video"
              :src="getYoutubeEmbedUrl('https://youtu.be/9Gb3GqzZl-k')"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen>
            </iframe>
          </div>
        </div>
      </main>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ConteudoIntroducaoPage',
    computed: {
      moduleId() {
        return this.$route.params.moduleId;
      }
    },
    methods: {
      getYoutubeEmbedUrl(videoUrl) {
        const videoId = videoUrl.split('youtu.be/')[1];
        return `https://www.youtube.com/embed/${videoId}`;
      }
    }
  }
  </script>
  
  <style scoped>
  .conteudo-introducao-page {
    padding: 0;
    height: 100vh;
    overflow: hidden;
  }
  
  .header-container {
    display: flex;
    align-items: center;
    position: relative;
  }
  
  .back-button {
    font-family: 'Montserrat', sans-serif;
    font-size: 1.2rem;
    font-weight: 600;
    padding: 8px 20px;
    background-color: var(--color-background);
    color: var(--color-black);
    border: none;
    cursor: pointer;
    box-shadow: 5px 5px 1px -1px var(--color-text-top);
    text-align: center;
    margin-right: 20px;
  }
  
  .title {
    color: var(--color-text-top);
    font-family: 'Montserrat', sans-serif;
    font-weight: 600;
    font-size: 2rem;
    margin: 10px 0;
  }
  
  .main-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: calc(100vh - 80px);
  }
  
  .video-container {
    width: 100%;
    height: 100%;
    position: relative;
  }
  
  .video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  
  .module-title {
    color: var(--color-black);
    font-family: 'Montserrat', sans-serif;
    font-size: 2rem;
    font-weight: 600;
    margin-bottom: 20px;
    position: relative;
    z-index: 1;
  }
  
  @media (max-width: 768px) {
    .back-button {
      font-size: 1.5rem;
    }
  
    .title {
      font-size: 1.6rem;
    }
  
    .module-title {
      font-size: 1.6rem;
    }
  }
  </style>  