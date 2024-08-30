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
  import vector from './assets/vector.png'
  import vector1 from './assets/vector1.png'
  import backgroundImage from './assets/Gym.jpg' 

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
  
  <Intro/>
  <MissionVision />
  <Excercise />
  <img src={uti} alt="UTI Image" class="uti-image absolute right-0 top-500 h-full object-right" />
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
  }
</style>
