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

<header class="fixed top-0 left-0 w-full z-50 px-6 py-8 md:px-16 lg:px-24 md:py-10 flex justify-between items-center bg-white/95 backdrop-blur-sm transition-all duration-300 text-black">
  <a href="/" class="flex items-center gap-2 hover:opacity-50 transition-opacity">
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor"/>
    </svg>
    <span class="text-lg md:text-xl font-normal tracking-wide">Sidegate</span>
  </a>

  <a href="#contact" class="text-sm font-normal hover:opacity-50 transition-opacity">
    Contact
  </a>
</header>
