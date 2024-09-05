<script>
  import exercisingImage from './assets/UT.png';

  let prompts = [
    { text: 'UTraining?', duration: 7000 },
    { text: 'Tu app de ejercicio y alimentación', duration: 5000 },
    { text: '¿Cómo puedo organizar mis ejercicios?', duration: 4000 },
    { text: '¿Cuánta proteína hay en 100g de pollo?', duration: 4000 }
  ];

  let currentPrompt = '';
  let promptIndex = 0;
  let charIndex = 0;
  let typingSpeed = 100;
  let erasingSpeed = 50;

  function type() {
    if (charIndex < prompts[promptIndex].text.length) {
      currentPrompt += prompts[promptIndex].text.charAt(charIndex);
      charIndex++;
      setTimeout(type, typingSpeed);
    } else {
      setTimeout(erase, prompts[promptIndex].duration);
    }
  }

  function erase() {
    if (charIndex > 0) {
      currentPrompt = currentPrompt.substring(0, charIndex - 1);
      charIndex--;
      setTimeout(erase, erasingSpeed);
    } else {
      promptIndex = (promptIndex + 1) % prompts.length;
      setTimeout(type, typingSpeed + 500);
    }
  }

  setTimeout(type, 500);
</script>

<section id="intro" class="intro-section flex flex-col md:flex-row items-center justify-center text-white py-24 px-6" style="min-height: 100vh;">
  <div class="w-full md:w-1/2 flex items-center justify-center md:justify-start mb-8 md:mb-0">
    <div class="text-center md:text-left max-w-full">
      <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl font-bold mb-4 leading-tight typing-text">
        {currentPrompt}
        <span class="typing-cursor">|</span>
      </h2>
    </div>
  </div>
  <div class="w-full md:w-1/2 flex items-center justify-center md:justify-end">
    <img src={exercisingImage} alt="Ejercitando" class="max-w-xs h-auto md:max-w-md lg:max-w-lg"/>
  </div>
</section>

<style>
  .intro-section {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    font-family: 'Roboto'
  }

  .typing-text {
    display: inline-block;
    font-weight: 600;
    line-height: 1.3; 
    margin-bottom: 0.8em; 
    border-right: 0.15em solid transparent; 
    white-space: normal;
    overflow: hidden;
    word-break: break-word;
  }

  .typing-cursor {
    font-weight: 100;
    font-size: 1.2em;
    color: #ffffff;
    animation: typing-cursor-blink 0.7s steps(40, end) infinite;
  }

  @keyframes typing-cursor-blink {
    0% { opacity: 1; }
    50% { opacity: 0; }
    100% { opacity: 1; }
  }
</style>
