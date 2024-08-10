<script>
    import backgroundImage from './assets/background-example.jpg'
</script>

<section  id="intro" class="intro-section bg-cover bg-center flex items-center justify-center text-white py-24 px-6" style="background-image: url('{backgroundImage}'); min-height: 100vh;">
  <div class="max-w-3xl text-left md:text-center">
    <h2 class="text-4xl font-bold mb-4 leading-tight">
      <span class="text-green-500">Donde la tecnología</span> y <span class="text-green-500">tus metas</span> se encuentran
    </h2>
    <p class="text-lg">
      uTraining ofrece una solución integral para mejorar tu vida fitness. La app permite registrar y monitorear tus ejercicios, incluyendo repeticiones y pesos, con gráficas interactivas que muestran tu progreso. También ofrece un seguimiento detallado de tu alimentación, registrando los alimentos consumidos y monitoreando macronutrientes para optimizar tu dieta. Además, un asistente inteligente tendrá en cuenta tus datos guardados en la app para recibir consultas pertinentes, y estará disponible para resolver cualquier duda que puedas tener, asegurando una optimización constante de tu programa de entrenamiento y alimentación.
    </p>
  </div>
</section>

<style>
.intro-section {
   position: relative;
   z-index: 1;
   width: 100%;
   height: 100vh;
   background-size: cover; 
   background-position: center;
   margin: 0; 
   padding: 0;
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
</style>