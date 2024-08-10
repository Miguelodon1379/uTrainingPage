<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import Header from "./Header.svelte"
  import Intro from "./Intro.svelte"
  import MissionVision from "./Mission-Vision.svelte"
  import Excercise from "./Excercise.svelte"
  import Food from "./Food.svelte"
  import Ai from "./Ai.svelte"
  import Glide from '@glidejs/glide'

  let prefix = 'U'
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
  <Header />
  <Intro />
  <MissionVision />
  <Excercise />
  <Food />
  <Ai />

  <h1>{prefix}{suffix}</h1>

</main>

<style>
 
</style>
