<section id="excercise" class="exercise-section flex items-center justify-center py-24 px-6" style="min-height: 100vh;">
  <div class="text-center w-full">
    <h2 class="text-4xl font-bold mb-4">¡Registra y Monitoriza tu Progreso!</h2>
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
            <source src="path/to/your/video.mp4" type="video/mp4">
            Your browser does not support the video tag.
          </video>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
.phone-frame {
  width: 300px;
  height: 600px;
  border-radius: 40px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  background-color: black;
  position: relative;
}

.phone-frame::before, .phone-frame::after {
  content: '';
  position: absolute;
  background: #333;
  border-radius: 50%;
}

.phone-frame::before {
  width: 60px;
  height: 60px;
  top: 10px;
  left: calc(50% - 30px);
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
  .exercise-section .flex {
    flex-direction: row;
  }
}
</style>

  