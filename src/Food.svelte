<section id="food" class="food-section flex items-center justify-center py-24 px-6" style="min-height: 100vh;">
    <div class="text-center">
      <h2 class="text-4xl font-bold mb-4">¡Controla Tu Alimentación y Mejora Tu Dieta!</h2>
      <div class="flex flex-col md:flex-row justify-center space-y-6 md:space-y-0 md:space-x-12">
        <div class="flex-1">
          <h3 class="text-2xl font-bold mb-2">Lleva un registro detallado de tus comidas:</h3>
          <ul class="text-lg list-disc list-inside">
            <li>Registra los alimentos que consumes diariamente.</li>
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
    </div>
  </section>
  
<style>
   .food-section {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh; 
      margin: 0; 
      padding: 0; 
    }
  
    .food-section h2{
      font-size: 2.25rem;
      margin-bottom: 4rem;
    }
    .food-section h3{
      margin-bottom: 4rem;
    }
    .food-section p, .food-section ul{
      font-size: 1.125rem;
    }
  
    .food-section .flex{
      display: flex;
      flex-direction: column;
    }
    .food-section .flex-1{
      flex: 1;
    }
    .food-section video{
      width: 100%;
      height: auto;
    }
    @media (min-width: 768px) {
      .food-section .flex{
        flex-direction: row;
      }
    }    
</style>