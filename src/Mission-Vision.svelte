<script>
  import vec1 from './assets/vector.png';
  import vec2 from './assets/vector1.png';
</script>

<section id="vision-mission" class="vision-mission-section flex items-center justify-center py-24 px-6" style="min-height: 100vh;">
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-1" />
  <img src={vec1} alt="Vector 1" class="absolute vec-img vec1-2" />
  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-1" />
  <img src={vec2} alt="Vector 2" class="absolute vec-img vec2-2" />

  <div class="text-center">
    <h2 class="text-8xl font-bold mb-8 outlined-text">Visión & Misión</h2>
    <p class="mb-8 mission-title">¿Qué estamos haciendo y por qué lo hacemos?</p>
    <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2 outlined-text">Nuestra Visión 👀</h3>
        <p class="text-lg mission-text">Ser la aplicación líder en el ámbito del fitness y la salud, reconocida por nuestra capacidad de integrar tecnología avanzada y personalización para ayudar a nuestros usuarios a alcanzar sus metas de manera efectiva y sostenible.</p>
      </div>
      <div class="flex-1">
        <h3 class="text-2xl font-bold mb-2 outlined-text">Nuestra Misión 🎯</h3>
        <p class="text-lg mission-text">Ofrecer una plataforma innovadora que revolucione la manera en que las personas gestionan y mejoran su vida fitness, proporcionando herramientas avanzadas y personalizadas que faciliten el seguimiento y logro de sus objetivos de salud y bienestar.</p>
      </div>
    </div>
  </div>
</section>

<style>
.vision-mission-section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh; 
  margin: 0; 
  padding: 0; 
}

.vec-img {
  max-width: 150px;
  opacity: 0.3;
  z-index: -1;
}

.vec1-1 {
  top: 10%;
  left: 5%;
}

.vec1-2 {
  bottom: 15%;
  right: 10%;
}

.vec2-1 {
  top: 20%;
  right: 15%;
}

.vec2-2 {
  bottom: 25%;
  left: 20%;
}

@media (min-width: 768px) {
  .vec-img {
    max-width: 300px;
  }
}

.outlined-text {
  color: white;
  text-shadow: 
    1px 1px 0 #708269, 
    -1px -1px 0 #708269, 
    1px -1px 0 #708269, 
    -1px 1px 0 #708269;
}

.mission-title {
  display: inline-block;
  background-color: rgba(112, 130, 105, 0.8); 
  color: white;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 1.125rem;
}

.mission-text {
  background-color: rgba(255, 255, 255, 0.8); 
  color: black;
  padding: 16px;
  border: 2px solid #708269;
  border-radius: 8px;
  margin-bottom: 1rem;
}

@media (min-width: 768px) {
  .vision-mission-section .flex {
    flex-direction: row;
  }
}
</style>
