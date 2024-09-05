<script>
  import svelteLogo from './assets/svelte.svg';
  import viteLogo from '/vite.svg';
  import Counter from './lib/Counter.svelte';
  import Header from "./Header.svelte";
  import Intro from "./Intro.svelte";
  import MissionVision from "./Mission-Vision.svelte";
  import Excercise from "./Excercise.svelte";
  import Food from "./Food.svelte";
  import Ai from "./Ai.svelte";
  import Download from "./download.svelte";
  import Footer from "./Footer.svelte";
  import uti from './assets/uti.png';
  import backgroundImage from './assets/background.jpg';
  import backgroundMision from './assets/Mision-Vision.jpg';  

  let prefix = 'U';
  let suffix = 'Hungry?';
  setInterval(function() {
    if (suffix === 'Hungry?') {
      prefix = 'U';
      suffix = 'Hungry';
    } else {
      prefix = 'U';
      suffix = 'Hungry?';
    }
  }, 2000);
</script>

<main>
  <div class="header-container">
    <Header />
  </div>
  
  <Intro />

  <div class="background-image-container">
    <img src={backgroundImage} alt="background Image" class="background-image" />
  </div>

  <div class="background-MisionVision-container">
    <img src={backgroundMision} alt="mision Image" class="background-image" />
  </div>

  <MissionVision />
  <Excercise />
  
  <img src={uti} alt="UTI Image" class="uti-image absolute right-0 top-1000 h-full object-right" />
  
  <Food />
  <Ai />
  <Download />

  <div class="footer-container">
    <Footer />
  </div>
</main>

<style>
  .header-container {
    display: none;
  }

  .footer-container {
    display: none;
  }

  .uti-image {
    display: none; 
  }

  .background-image-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1; 
    overflow: hidden; 
  }

  .background-image-container .background-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center
  }

  .background-image-container::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5); 
    z-index: 1; 
  }

  .background-MisionVision-container {
    position: absolute;
    top: 100vh; 
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1; 
    overflow: hidden; 
  }


  .background-MisionVision-container .background-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  @media (min-width: 1024px) {
    .header-container {
      display: block;
    }

    .uti-image {
      display: block; 
    }
  }

@media (max-width: 1023px) {
    .footer-container {
        display: block;
    }

    .background-image-container,
    .background-MisionVision-container {
        position: absolute;
        width: 100%;
        height: 100%;
        z-index: -1;
        overflow: hidden;
    }

    .background-image-container {
        top: 0;
    }

    .background-MisionVision-container {
        top: 100vh; 
        height: 120vh; 
    }

    .background-image-container::before{
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.3); 
        z-index: 1; 
    }

    .background-image,
    .background-MisionVision-container .background-image {
        width: 100%;
        height: 100%;
        object-fit: cover; 
        object-position: center; 
    }
}

</style>
