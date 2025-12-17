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
  <a href="/" class="text-xl md:text-2xl font-normal tracking-wide z-10">Calamos Investments</a>
  
  <button class="absolute left-1/2 -translate-x-1/2 top-6 md:top-8 text-lg font-normal hover:opacity-70 transition-opacity z-10">
    Menu
  </button>

  <button class="hover:opacity-70 transition-opacity z-10" aria-label="Search">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M11 19C15.4183 19 19 15.4183 19 11C19 6.58172 15.4183 3 11 3C6.58172 3 3 6.58172 3 11C3 15.4183 6.58172 19 11 19Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M21 21L16.65 16.65" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </button>
</header>
