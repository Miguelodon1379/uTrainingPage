<script>
    import { onMount } from 'svelte';

    let activeSection = 'intro'; // Sección activa inicial

    function scrollToSection(event, sectionId) {
      event.preventDefault()
      const section = document.getElementById(sectionId)
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' })
        activeSection = sectionId
      }
    }

    onMount(() => {
    const sections = document.querySelectorAll('section');

    const observerOptions = {
      root: null,
      rootMargin: '0px',
      threshold: 0.5, // Sección está activa cuando 50% es visible
    };

    const observerCallback = (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          activeSection = entry.target.id;
        }
      });
    };

    const observer = new IntersectionObserver(observerCallback, observerOptions);

    sections.forEach(section => {
      observer.observe(section);
    });

    return () => {
      observer.disconnect();
    };
  });
</script>


<!-- Top bar -->
<div class="border-b border-slate-200 bg-slate-100 z-40 fixed top-0 left-0 right-0">
    <div class="mx-auto grid w-full max-w-full grid-cols-4 gap-6 py-2 px-6 text-sm text-slate-500 md:grid-cols-8 lg:max-w-5xl lg:grid-cols-12 xl:max-w-7xl 2xl:max-w-[96rem]">
      <div class="items-center justify-end col-span-2 gap-6 md:col-span-4 lg:col-span-6">
        <div class="flex items-center justify-end gap-4">
          <a href="javascript:void(0)" class="transition-colors duration-300 hover:text-emerald-500">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 48 48" height="16" width="16" role="graphics-symbol" aria-labelledby="title-tb03 desc-tb03">
              <title id="title-tb03">Icon title</title>
              <desc id="desc-tb03">A more detailed description of the icon</desc>
              <path fill="currentColor" {...{"fillRule": "evenodd"}} d="M47.5 24C47.5 11.288 36.712 0.5 24 0.5S0.5 11.288 0.5 24C0.5 35.449 9.074 44.699 20.062 47.07V30.546H14.672v-6.545h5.39v-4.833c0-5.504 3.288-8.54 8.312-8.54 2.409 0 4.925.43 4.925.43v5.41h-2.774c-2.734 0-3.584 1.697-3.584 3.444v4.088h6.094l-.974 6.546h-5.12v16.524C38.926 44.7 47.5 35.448 47.5 24Z" clipRule="evenodd" />
            </svg>
            
            
          </a>
          <a href="javascript:void(0)" class="transition-colors duration-300 hover:text-emerald-500">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 48 48" height="16" width="16" role="graphics-symbol" aria-labelledby="title-tb02 desc-tb02">
              <title id="title-tb02">Icon title</title>
              <desc id="desc-tb02">A more detailed description of the icon</desc>
              <path fill="currentColor" d="M34.7229 4.69819C36.9179 5.13151 38.8231 6.226 39.9574 7.46121L44.8741 7.22772C46.162 7.16656 46.9576 8.61264 46.216 9.66758L42.8041 14.5217C43.7777 35.6815 22.2547 49.0961 4.54954 41.2208C3.75067 40.8654 3.58181 40.0439 3.74682 39.4029C3.91015 38.7685 4.4337 38.1304 5.23631 38.0329C7.74782 37.7279 10.886 36.8951 13.5309 34.8102C11.3351 34.4801 8.87383 33.2203 6.77118 31.5522C4.25179 29.5535 2.11595 26.8651 1.53319 24.2321C1.41942 23.7181 1.60805 23.2504 1.94754 22.9478C2.27981 22.6517 2.75116 22.5146 3.22643 22.6022C4.4998 22.8369 6.44397 23.1705 7.93366 23.3225C7.82715 23.2095 7.71399 23.0872 7.59534 22.9561C6.83881 22.1198 5.85466 20.9171 4.947 19.4528C3.13974 16.5372 1.58717 12.5021 2.86967 8.24191C3.04524 7.65872 3.52191 7.3215 4.02883 7.2399C4.52724 7.15967 5.07712 7.31911 5.46709 7.72851C7.80814 10.1862 13.7896 15.4057 22.914 16.1638C22.5823 14.0277 22.368 9.45707 27.1303 6.0147C29.4244 4.33991 32.2428 3.81669 34.7229 4.69819Z" />
            </svg>
          </a>
          <a href="javascript:void(0)" class="transition-colors duration-300 hover:text-emerald-500">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 48 48" height="16" width="16" role="graphics-symbol" aria-labelledby="title-tb03 desc-tb03">
              <title id="title-tb03">Icon title</title>
              <desc id="desc-tb03">A more detailed description of the icon</desc>
              <path fill="currentColor" {...{"fillRule": "evenodd"}} d="M47.5 24C47.5 11.288 36.712 0.5 24 0.5S0.5 11.288 0.5 24C0.5 35.449 9.074 44.699 20.062 47.07V30.546H14.672v-6.545h5.39v-4.833c0-5.504 3.288-8.54 8.312-8.54 2.409 0 4.925.43 4.925.43v5.41h-2.774c-2.734 0-3.584 1.697-3.584 3.444v4.088h6.094l-.974 6.546h-5.12v16.524C38.926 44.7 47.5 35.448 47.5 24Z" clipRule="evenodd" />
            </svg>
            
          </a>
        </div>
      </div>
    </div>
</div>
  
<!-- Main header -->
<header aria-label="Site Header" class="bg-white fixed top-8 left-0 right-0 z-50">
    <div class="mx-auto flex h-16 max-w-screen-xl items-center gap-8 px-4 sm:px-6 lg:px-8">
      <a class="block text-teal-600" href="/">
        <span class="sr-only">Home</span>
        <svg class="h-8" viewBox="0 0 28 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0.41 10.3847C1.14777 7.4194 2.85643 4.7861 5.2639 2.90424C7.6714 1.02234 10.6393 0 13.695 0C16.7507 0 19.7186 1.02234 22.1261 2.90424C24.5336 4.7861 26.2422 7.4194 26.98 10.3847H25.78C23.8492 10.3847 21.9924 11.1581 20.6265 12.5112C19.2607 13.8643 18.51 15.7086 18.51 17.6284C18.51 19.5483 19.2607 21.3926 20.6265 22.7457C21.9924 24.0988 23.8492 24.8722 25.78 24.8722H26.98C26.2422 27.8375 24.5336 30.4708 22.1261 32.3527C19.7186 34.2346 16.7507 35.2569 13.695 35.2569C10.6393 35.2569 7.6714 34.2346 5.2639 32.3527C2.85643 30.4708 1.14777 27.8375 0.41 24.8722H1.61C3.54083 24.8722 5.39761 24.0988 6.76347 22.7457C8.12932 21.3926 8.88 19.5483 8.88 17.6284C8.88 15.7086 8.12932 13.8643 6.76347 12.5112C5.39761 11.1581 3.54083 10.3847 1.61 10.3847H0.41ZM13.695 1.67772C11.0733 1.67772 8.56472 2.62982 6.63657 4.34204C4.70843 6.05427 3.47285 8.41861 3.064 11.0122H4.324C5.91583 11.0122 7.43108 11.7185 8.51525 12.9475C9.59942 14.1765 10.156 15.8137 10.156 17.5172C10.156 19.2206 9.59942 20.8579 8.51525 22.0869C7.43108 23.3158 5.91583 24.0222 4.324 24.0222H3.064C3.47285 26.6157 4.70843 28.98 6.63657 30.6923C8.56472 32.4045 11.0733 33.3566 13.695 33.3566C16.3167 33.3566 18.8253 32.4045 20.7534 30.6923C22.6816 28.98 23.9172 26.6157 24.326 24.0222H23.066C21.4742 24.0222 19.9589 23.3158 18.8747 22.0869C17.7906 20.8579 17.234 19.2206 17.234 17.5172C17.234 15.8137 17.7906 14.1765 18.8747 12.9475C19.9589 11.7185 21.4742 11.0122 23.066 11.0122H24.326C23.9172 8.41861 22.6816 6.05427 20.7534 4.34204C18.8253 2.62982 16.3167 1.67772 13.695 1.67772Z" fill="#0EA5E9"/>
        </svg>
      </a>
      <div class="flex flex-1 items-center justify-between">
        <nav aria-label="Site Nav" class="hidden md:flex md:gap-4 lg:gap-8">
         <a
            href="#intro"
            on:click="{(e) => scrollToSection(e, 'intro')}"
            class:text-gray-700={activeSection === 'intro'}
            class:bg-gray-100={activeSection === 'intro'}
         >
            Inicio
         </a>
         <a
            href="#vision-mission"
            on:click="{(e) => scrollToSection(e, 'vision-mission')}"
            class:text-gray-700={activeSection === 'vision-mission'}
            class:bg-gray-100={activeSection === 'vision-mission'}
         >
            Misión y Visión
         </a>
         <a
            href="#excercise"
            on:click="{(e) => scrollToSection(e, 'excercise')}"
            class:text-gray-700={activeSection === 'excercise'}
            class:bg-gray-100={activeSection === 'excercise'}
         >
            Tracks
         </a>
         <a
            href="#ai"
            on:click="{(e) => scrollToSection(e, 'ai')}"
            class:text-gray-700={activeSection === 'ai'}
            class:bg-gray-100={activeSection === 'ai'}
         >
            Nuestra IA
         </a>
         <a
            href="#contact"
            on:click="{(e) => scrollToSection(e, 'contact')}"
            class:text-gray-700={activeSection === 'contact'}
            class:bg-gray-100={activeSection === 'contact'}
         >
            Cómo descargarla
         </a>
        </nav>
        <div class="flex items-center gap-4">
          <a href="https://play.google.com" class="inline-flex h-12 min-w-36 items-center justify-start gap-2 whitespace-nowrap rounded border border-slate-900 px-2.5 text-sm font-semibold tracking-wide text-slate-900 transition duration-300 hover:border-slate-950 focus:border-slate-950 focus-visible:outline-none mt-4 md:mt-0 ml-12"> <!-- Cambia 'mr-6' por 'ml-8' -->
            <svg width="30" height="30" class="w-8 h-8" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" role="graphics-symbol" aria-label="Google play icon">
              <path d="M21.9219 19.6222L27.8405 13.7036L8.72367 2.95928C7.45668 2.27475 6.26976 2.17868 5.22895 2.92726L21.9219 19.6222ZM28.8316 26.5339L34.9843 23.0732C36.1853 22.4007 36.8438 21.4479 36.8438 20.3911C36.8438 19.3363 36.203 18.3993 35.0041 17.7267L29.4337 14.5983L23.1452 20.8495L28.8316 26.5339ZM4.20016 4.38239C4.07206 4.7767 4 5.21704 4 5.69941V35.1322C4 35.8948 4.16813 36.5513 4.47237 37.0738L20.6789 20.8652L4.20016 4.38239ZM21.9219 22.1061L5.8054 38.2246C6.11364 38.3427 6.4459 38.4048 6.79617 38.4048C7.42065 38.4048 8.07116 38.2206 8.73367 37.8524L27.258 27.4503L21.9219 22.1061Z" fill="currentColor"></path>
            </svg>
            <span class="flex flex-col">
              <span class="text-xs font-normal">Get it on</span>
              <span class="text-base">Google Play</span>
            </span>
          </a>
        </div>
      </div>
    </div>
</header>

<style>
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
      .text-gray-700 { color: #374151; }
      .bg-gray-100 { background-color: #f3f4f6; }
</style>