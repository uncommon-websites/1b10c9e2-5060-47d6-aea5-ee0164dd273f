<script lang="ts">
  import { onMount } from 'svelte';

  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 50;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<header class="fixed top-0 left-0 w-full z-50 px-5 py-6 md:px-10 md:py-8 flex justify-between items-start bg-white/90 backdrop-blur-sm transition-all duration-300 text-black">
  <a href="/" class="flex items-center gap-2 z-10 hover:opacity-70 transition-opacity">
    <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor"/>
    </svg>
    <span class="text-xl md:text-2xl font-normal tracking-wide">Sidegate</span>
  </a>
  
  <button class="absolute left-1/2 -translate-x-1/2 top-6 md:top-8 text-lg font-normal hover:opacity-70 transition-opacity z-10">
    Menu
  </button>

  <a href="#contact" class="text-sm md:text-base font-normal hover:opacity-70 transition-opacity z-10">
    Contact
  </a>
</header>
