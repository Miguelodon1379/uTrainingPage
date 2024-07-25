<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import backgroundImage from './assets/background-example.jpg'
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
  <header class="fixed top-0 left-0 w-full bg-white flex justify-between items-center p-4 border-b border-gray-200 z-50">
    <div class="flex space-x-4 ml-6">
      <a href="Aqui va el boton1" class="header-button">Instagram</a>
      <a href="Aqui va el boton2" class="header-button">Facebook</a>
      <a href="Aqui va el boton3" class="header-button">TikTok</a>
    </div>
    <h1 class="flex-1 text-center text-xl font-bold text-black">UTraining</h1>
    <a href="https://play.google.com" class="inline-flex h-12 min-w-36 items-center justify-start gap-2 whitespace-nowrap rounded border border-slate-900 px-2.5 text-sm font-semibold tracking-wide text-slate-900 transition duration-300 hover:border-slate-950 focus:border-slate-950 focus-visible:outline-none mt-4 md:mt-0 mr-6">
      <svg width="30" height="30" class="w-8 h-8" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" role="graphics-symbol" aria-label="Google play icon">
        <path d="M21.9219 19.6222L27.8405 13.7036L8.72367 2.95928C7.45668 2.27475 6.26976 2.17868 5.22895 2.92726L21.9219 19.6222ZM28.8316 26.5339L34.9843 23.0732C36.1853 22.4007 36.8438 21.4479 36.8438 20.3911C36.8438 19.3363 36.203 18.3993 35.0041 17.7267L29.4337 14.5983L23.1452 20.8495L28.8316 26.5339ZM4.20016 4.38239C4.07206 4.7767 4 5.21704 4 5.69941V35.1322C4 35.8948 4.16813 36.5513 4.47237 37.0738L20.6789 20.8652L4.20016 4.38239ZM21.9219 22.1061L5.8054 38.2246C6.11364 38.3427 6.4459 38.4048 6.79617 38.4048C7.42065 38.4048 8.07116 38.2206 8.73367 37.8524L27.258 27.4503L21.9219 22.1061Z" fill="currentColor"></path>
      </svg>
      <span class="flex flex-col">
        <span class="text-xs font-normal">Get it on</span>
        <span class="text-base">Google Play</span>
      </span>
    </a>
  </header>
  
  <section class="intro-section bg-cover bg-center flex items-center justify-center text-white py-24 px-6" style="background-image: url('{backgroundImage}');">
    <div class="max-w-3xl text-left md:text-center">
      <h2 class="text-4xl font-bold mb-4 leading-tight">
        <span class="text-green-500">Donde la tecnología</span> y <span class="text-green-500">tus metas</span> se encuentran
      </h2>
      <p class="text-lg">
        uTraining ofrece una solución integral para mejorar tu vida fitness. La app permite registrar y monitorear tus ejercicios, incluyendo repeticiones y pesos, con gráficas interactivas que muestran tu progreso. También ofrece un seguimiento detallado de tu alimentación, registrando los alimentos consumidos y monitoreando macronutrientes para optimizar tu dieta. Además, un asistente inteligente tendrá en cuenta tus datos guardados en la app para recibir consultas pertinentes, y estará disponible para resolver cualquier duda que puedas tener, asegurando una optimización constante de tu programa de entrenamiento y alimentación.
      </p>
    </div>
  </section>

  <section class="vision-mission-section py-24 px-6">
    <h2 class="text-4xl font-bold mb-4 text-center">Visión & Misión</h2>
    <p class="text-center mb-8">¿Qué estamos haciendo y por qué lo hacemos?.</p>
    <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2">Nuestra Visión 👀</h3>
        <p class="text-lg">Ser la aplicación líder en el ámbito del fitness y la salud, reconocida por nuestra capacidad de integrar tecnología avanzada y personalización para ayudar a nuestros usuarios a alcanzar sus metas de manera efectiva y sostenible.</p>
      </div>
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2">Nuestra Misión 🎯</h3>
        <p class="text-lg">Ofrecer una plataforma innovadora que revolucione la manera en que las personas gestionan y mejoran su vida fitness, proporcionando herramientas avanzadas y personalizadas que faciliten el seguimiento y logro de sus objetivos de salud y bienestar.</p>
      </div>
    </div>
  </section>
 
  <section class="exercise-section py-24 px-6">
    <h2 class="text-4xl font-bold mb-4 text-center">¡Registra y Monitoriza tu Progreso!</h2>
    <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2">Lleva un control de tus rutinas con nuestro track de ejercicios:</h3>
        <ul class="text-lg list-disc list-inside">
          <li>Registra tu rutina de ejercicios.</li>
          <li>Visualiza tu progreso con gráficas interactivas.</li>
          <li>Alcanza tus metas viendo tu evolución día a día.</li>
        </ul>
        <p class="text-lg mt-4">¡Mantente motivado y enfocado en tus objetivos con nuestro seguimiento personalizado!</p>
      </div>
      <div class="flex-1">
        <video class="w-full" autoplay muted loop controls>
          <source src="path/to/your/video.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
  </section>

  <section class="food-section py-24 px-6">
    <h2 class="text-4xl font-bold mb-4 text-center">¡Controla Tu Alimentación y Mejora Tu Dieta!</h2>
    <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2">Lleva un registro detallado de tus comidas:</h3>
        <ul class="text-lg list-disc list-inside">
          <li>Registra los alimentos que consumes diariamente. </li>
          <li>Visualiza tu ingesta con gráficas interactivas.</li>
          <li>Optimiza tu dieta para alcanzar tus objetivos de salud y fitness.</li>
        </ul>
        <p class="text-lg mt-4">¡Toma el control de tu nutrición y transforma tu cuerpo de manera saludable!</p>
      </div>
      <div class="flex-1">
        <video class="w-full" autoplay muted loop controls>
          <source src="path/to/your/video.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
  </section>

  <section class="ai-section py-24 px-6">
    <h2 class="text-4xl font-bold mb-4 text-center">Potencia tu Transformación con la Ayuda de IA</h2>
    <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2">Inteligencia Artificial a tu servicio Rutinas Personalizadas: </h3>
        <ul class="text-lg list-disc list-inside">
          <li>Según tus objetivos, nuestra IA te proporcionará rutinas de ejercicios y planes de alimentación adaptados a tus necesidades.</li>
          <li>Asistencia Continua: Resuelve tus dudas en cualquier momento con la ayuda de nuestra IA.</li>
        </ul>
        <p class="text-lg mt-4">¡Descubre una nueva forma de alcanzar tus metas con la tecnología más avanzada!</p>
      </div>
      <div class="flex-1">
        <video class="w-full" autoplay muted loop controls>
          <source src="path/to/your/video.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
  </section>

  <div class="mt-20">
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>{prefix}{suffix}</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
  .header-button {
    font-weight: 500;
    color: #333;
    background: none;
    border: none;
    cursor: pointer;
    transition: color 0.3s;
    text-decoration: none;
  }
  .header-button:hover {
    color: #000;
  }
  .intro-section {
    position: relative;
    z-index: 1;
    width: 100%;
    background-size: cover; 
    background-position: center; 
    margin-bottom: 4rem;
  }
  .intro-section:before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5); 
    z-index: -1;
  }
  .vision-mission-section {
    text-align: center;
    margin-top: 4rem; 
    margin-bottom: 4rem; 
  }
  .exercise-section, .food-section, .ai-section {
    text-align: justify;
    margin-top: 4rem; 
    margin-bottom: 4rem; 
  }

  .vision-mission-section h2{
    font-size: 2.25rem;
    margin-bottom: 1rem;
  }

  .exercise-section h2, .food-section h2, .ai-section h2 {
    font-size: 2.25rem;
    margin-bottom: 4rem;
  }
  .exercise-section h3, .food-section h3, .ai-section h3 {
    margin-bottom: 4rem;
  }
  .vision-mission-section p, .exercise-section p, .exercise-section ul, .food-section p, .food-section ul, .ai-section p, .ai-section ul {
    font-size: 1.125rem;
  }

  .vision-mission-section .flex, .exercise-section .flex, .food-section .flex, .ai-section .flex {
    display: flex;
    flex-direction: column;
  }
  .vision-mission-section .flex-1, .exercise-section .flex-1, .food-section .flex-1, .ai-section .flex-1 {
    flex: 1;
  }
  .exercise-section video, .food-section video, .ai-section video {
    width: 100%;
    height: auto;
  }
  @media (min-width: 768px) {
    .vision-mission-section .flex, .exercise-section .flex, .food-section .flex, .ai-section .flex {
      flex-direction: row;
    }
  }
</style>
