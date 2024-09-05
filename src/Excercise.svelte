<script>
  import background from './assets/bckgrnd-all.png';
  import vec1 from './assets/vect1.png';
  import vec2 from './assets/vect2.png';
  import vec3 from './assets/vect3.png';
  import video from './assets/Registro-ejercicio.mp4';
</script>

<section id="excercise" class="exercise-section flex items-center justify-center py-24 px-6" style="min-height: 100vh;">
  <img src={background} alt="Background" class="absolute background-image" />
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-1" />
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-2" />

  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-1" />
  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-2" />

  <img src={vec3} alt="Vector 3" class="absolute vec-img vec3-1" />
  <img src={vec3} alt="Vector 3" class="absolute vec-img vec3-2" />

  <div class="text-center w-full">
    <h2 class="styled-heading text-4xl font-bold mb-4">¡Registra y Monitoriza tu Progreso!</h2>
    <div class="flex flex-col md:flex-row justify-center md:justify-between space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1 flex items-center justify-center md:justify-start" style="min-height: 60vh;">
        <div>
          <h3 class="text-2xl font-bold mb-2">Lleva un control de tus rutinas con nuestro track de ejercicios:</h3>
          <ul class="text-lg list-disc list-inside">
            <li>Registra tu rutina de ejercicios.</li>
            <li>Visualiza tu progreso con gráficas interactivas.</li>
            <li>Alcanza tus metas viendo tu evolución día a día.</li>
          </ul>
          <p class="text-lg mt-4">¡Mantente motivado y enfocado en tus objetivos con nuestro seguimiento personalizado!</p>
        </div>
      </div>
      <div class="flex-1 flex justify-center">
        <div class="phone-frame">
          <video class="w-full h-full" autoplay muted loop controls>
            <source src={video} type="video/mp4">
            Your browser does not support the video tag.
          </video>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
.exercise-section {
  position: relative;
}

.background-image {
  display: block;
  opacity: 0.3;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
}

.vec-img {
  max-width: 300px;
  opacity: 0.2;
  z-index: -1;
}

.vec1-1 {
  top: 15%;
  left: 10%;
}

.vec1-2 {
  bottom: 15%;
  right: 15%;
}

.vec2-1 {
  top: 25%;
  right: 20%;
}

.vec2-2 {
  bottom: 25%;
  left: 20%;
}

.vec3-1 {
  top: 50%;
  left: 40%;
  transform: translateX(-50%);
}

.vec3-2 {
  bottom: 50%;
  right: 35%;
  transform: translateX(50%);
}

@media (min-width: 768px) {
  .background-image {
    display: none;
  }

  .vec-img {
    display: block;
  }
}

@media (max-width: 767px) {
  .background-image {
    display: block;
  }

  .vec-img {
    display: none;
  }

  .exercise-section {
    background-position: top; 
  }

  .phone-frame {
    width: 250px;
    height: 500px;
  }
}

.styled-heading {
  color: white; 
  text-shadow: 
    -1px -1px 0 #708269,   
    1px -1px 0 #708269,    
    -1px 1px 0 #708269,    
    1px 1px 0 #708269;     
}

.phone-frame {
  width: 300px;
  height: 600px;
  border-radius: 40px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  background-color: black;
  position: relative;
}

.phone-frame::before,
.phone-frame::after {
  content: '';
  position: absolute;
  background: #333;
  border-radius: 50%;
}

.phone-frame::after {
  width: 100px;
  height: 5px;
  bottom: 10px;
  left: calc(50% - 50px);
}

video {
  object-fit: cover;
}
</style>