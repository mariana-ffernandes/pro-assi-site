<template>
    <div class="frequently-questions-content">
      <header class="header-container">
        <router-link to="/frequently-questions" class="back-button">← voltar</router-link>
        <h1 class="title">Dúvidas Frequentes</h1>
      </header>
      <main class="main-container">
        <div class="video-container">
          <iframe 
            :src="getYoutubeEmbedUrl(videoUrl)" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen 
            class="video-iframe"
          ></iframe>
        </div>
      </main>
    </div>
  </template>  
  
  <script>
  export default {
    name: 'FrequentlyQuestionsContent',
    computed: {
      videoUrl() {
        return this.$route.params.videoUrl;
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
  .frequently-questions-content {
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

  .video-iframe {
  width: 100% !important;
  height: 100% !important;
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
  