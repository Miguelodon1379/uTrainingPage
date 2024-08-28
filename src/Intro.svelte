<script>
  import backgroundImage from './assets/Gym.jpg'
  import exercisingImage from './assets/UT.png'

  let prompts = ['UTraining', 'UTraining?', 'Track it!', 'Stay Fit!', 'Keep Going!'];
  let currentPrompt = '';
  let promptIndex = 0;
  let charIndex = 0;
  let typingSpeed = 100;
  let erasingSpeed = 50;
  let newPromptDelay = 2000;

  function type() {
      if (charIndex < prompts[promptIndex].length) {
          currentPrompt += prompts[promptIndex].charAt(charIndex);
          charIndex++;
          setTimeout(type, typingSpeed);
      } else {
          setTimeout(erase, newPromptDelay);
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

  setTimeout(type, newPromptDelay + 250);
</script>

<section id="intro" class="intro-section bg-cover bg-center flex flex-col md:flex-row items-center justify-center text-white py-24 px-6" style="background-image: url('{backgroundImage}'); min-height: 100vh;">
<div class="w-full md:w-1/2 flex items-center justify-center md:justify-start mb-8 md:mb-0">
  <div class="text-center md:text-left">
    <h2 class="text-4xl md:text-6xl font-bold mb-4 leading-tight typing-text">
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
.typing-text {
 display: inline-block;
 border-right: 0.15em solid #ffffff;
 white-space: nowrap;
 overflow: hidden;
 animation: typing-cursor-blink 0.7s steps(40, end) infinite;
}

.typing-cursor {
 font-weight: 100;
 font-size: 1.2em;
 color: #ffffff;
 animation: typing-cursor-blink 0.7s steps(40, end) infinite;
}

@keyframes typing-cursor-blink {
 from { border-color: transparent; }
 to { border-color: #ffffff; }
}
</style>
