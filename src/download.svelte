<script>
  import slide1 from './assets/1.png';
  import slide2 from './assets/2.png';
  import slide3 from './assets/3.png';
  import slide4 from './assets/4.png';

  let currentSlide = 0;
  const slides = [slide1, slide2, slide3, slide4];

  function nextSlide() {
    currentSlide = (currentSlide + 1) % slides.length;
  }

  function prevSlide() {
    currentSlide = (currentSlide - 1 + slides.length) % slides.length;
  }
</script>

<section id="download" class="relative w-full py-24 px-6">
  <div class="carousel flex w-full overflow-hidden">
    {#each slides as slide, index}
      <div
        class="carousel-item w-full flex-shrink-0"
        style="transform: translateX({-currentSlide * 100}%);">
        <img src={slide} alt={"slide " + (index + 1)} class="w-full h-full object-cover" />
      </div>
    {/each}
  </div>
  <div class="absolute left-5 right-5 top-1/2 flex -translate-y-1/2 transform justify-between">
    <button on:click={prevSlide} class="btn btn-circle">❮</button>
    <button on:click={nextSlide} class="btn btn-circle">❯</button>
  </div>
</section>

<style>
  .carousel-item {
    min-width: 100%; 
    transition: transform 0.5s ease-in-out;
  }

  .btn:focus {
    outline: none;
  }

  .btn:active {
    background-color: transparent;
  }

  .btn:hover {
    background-color: #292929; /* O cualquier color que prefieras para el hover */
  }
</style>
