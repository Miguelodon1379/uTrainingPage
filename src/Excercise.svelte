<section id="excercise" class="exercise-section flex items-center justify-center py-24 px-6" style="min-height: 100vh;">
    <div class="text-center">
      <h2 class="text-4xl font-bold mb-4">¡Registra y Monitoriza tu Progreso!</h2>
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
    </div>
  </section>
  
  <style>
  .exercise-section {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh; 
      margin: 0; 
      padding: 0; 
    }
  
    .exercise-section h2{
      font-size: 2.25rem;
      margin-bottom: 4rem;
    }
    .exercise-section h3{
      margin-bottom: 4rem;
    }
    .exercise-section p, .exercise-section ul{
      font-size: 1.125rem;
    }
  
    .exercise-section .flex{
      display: flex;
      flex-direction: column;
    }
    .exercise-section .flex-1{
      flex: 1;
    }
    .exercise-section video{
      width: 100%;
      height: auto;
    }
    @media (min-width: 768px) {
      .exercise-section .flex{
        flex-direction: row;
      }
    }
  </style>
  
  