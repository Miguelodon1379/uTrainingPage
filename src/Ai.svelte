<script>
  import vec1 from './assets/vect1.png';
  import vec2 from './assets/vect2.png';
  import vec3 from './assets/vect3.png';
  import video from './assets/Chat-Uti.mp4';
</script>

<section id="ai" class="ai-section flex items-center justify-center py-24 px-6 relative" style="min-height: 100vh;">
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-1" />
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-2" />

  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-1" />
  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-2" />

  <img src={vec3} alt="Vector 3" class="absolute vec-img vec3-1" />
  <img src={vec3} alt="Vector 3" class="absolute vec-img vec3-2" />

  <div class="text-center w-full">
    <h2 class="styled-heading text-4xl font-bold mb-4">Potencia tu Transformación con la Ayuda de IA</h2>
    <div class="flex flex-col md:flex-row justify-center md:justify-between items-center space-y-6 md:space-y-0 md:space-x-12">
      
      <div class="flex-1 flex items-center justify-center md:justify-start" style="min-height: 60vh;">
        <div>
          <h3 class="text-2xl font-bold mb-2">Inteligencia Artificial a tu servicio Rutinas Personalizadas:</h3>
          <ul class="text-lg list-disc list-inside">
            <li>Según tus objetivos, nuestra IA te proporcionará rutinas de ejercicios y planes de alimentación adaptados a tus necesidades.</li>
            <li>Asistencia Continua: Resuelve tus dudas en cualquier momento con la ayuda de nuestra IA.</li>
          </ul>
          <p class="text-lg mt-4">¡Descubre una nueva forma de alcanzar tus metas con la tecnología más avanzada!</p>
        </div>
      </div>
      
      <div class="flex-1 flex justify-center">
        <div class="phone-frame">
          <video class="w-full h-full" autoplay muted loop controls>
            <source src={video} type="video/mp4">
            Tu navegador no soporta el elemento de video.
          </video>
        </div>
      </div>
      
    </div>
  </div>
</section>

<style>
.ai-section {
  position: relative;
}

.styled-heading {
  color: white; 
  text-shadow: 
    -1px -1px 0 #708269,   
    1px -1px 0 #708269,    
    -1px 1px 0 #708269,    
    1px 1px 0 #708269;     
}

.vec-img {
  max-width: 300px;
  opacity: 0.3;
  z-index: -1;
}

.vec1-1 {
  top: 10%;
  left: 5%;
}

.vec1-2 {
  bottom: 10%;
  right: 5%;
}

.vec2-1 {
  top: 20%;
  right: 10%;
}

.vec2-2 {
  bottom: 20%;
  left: 5%;
}

.vec3-1 {
  top: 50%;
  left: 30%;
  transform: translateX(-50%);
}

.vec3-2 {
  bottom: 50%;
  right: 30%;
  transform: translateX(50%);
}

@media (max-width: 767px) {
  .vec-img {
    max-width: 100px;
    opacity: 0.7;
  }
  
  .vec1-1 {
    top: 5%;
    left: 2%;
  }

  .vec1-2 {
    bottom: 5%;
    right: 2%;
  }

  .vec2-1 {
    top: 15%;
    right: 5%;
  }

  .vec2-2 {
    bottom: 15%;
    left: 5%;
  }

  .vec3-1 {
    top: 45%;
    left: 20%;
    transform: translateX(-50%);
  }

  .vec3-2 {
    bottom: 45%;
    right: 20%;
    transform: translateX(50%);
  }
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

@media (min-width: 768px) {
  .ai-section .flex {
    flex-direction: row;
  }
}
</style>
