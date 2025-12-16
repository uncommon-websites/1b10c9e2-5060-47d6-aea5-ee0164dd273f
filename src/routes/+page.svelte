<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import Section from "$lib/components/Section.svelte";
  
  const strategies = [
    "Single-Family Rentals",
    "Build-to-Rent Communities",
    "Homebuilding & Development",
    "Value-Add Operations",
    "Capital Structure Optimization"
  ];

  const insights = [
    {
      date: "Q4 2024",
      title: "Structural Undersupply in U.S. Housing: A First-Principles Analysis",
      image: "/generated/image-modern-single-family-rental-home-with-cl-1765733826118-0.webp"
    },
    {
      date: "Q3 2024",
      title: "Operational Alpha Through Value-Add Property Management",
      image: "/generated/image-property-management-professional-inspect-1765733837035-5.webp"
    },
    {
      date: "Q2 2024",
      title: "Market-Cycle Resilient Returns: Our Contrarian Investment Approach",
      image: "/generated/image-professional-investment-team-analyzing-d-1765733835001-4.webp"
    }
  ];

  const portfolioCompanies = [
    { name: "Sidegate SFR", desc: "Single-family rental operations", highlight: true },
    { name: "Sidegate BTR", desc: "Build-to-rent community development", highlight: true },
    { name: "Sidegate Homebuilding", desc: "Residential development and construction", highlight: true },
    { name: "Southeast Portfolio", desc: "High-growth market focus", highlight: false },
    { name: "Sunbelt Expansion", desc: "Strategic market positioning", highlight: false },
    { name: "Value-Add Platform", desc: "Operational improvement initiatives", highlight: false }
  ];
  let carousel: HTMLElement;

  import { onMount } from 'svelte';
  
  onMount(() => {
    if (carousel) {
      const centerImage = carousel.children[1] as HTMLElement;
      if (centerImage) {
        const scrollLeft = centerImage.offsetLeft - (carousel.clientWidth - centerImage.clientWidth) / 2;
        carousel.scrollLeft = scrollLeft;
      }
    }
  });
</script>

<Header />

<main class="pt-40 md:pt-48 pb-32 px-6 md:px-16 lg:px-24 font-sans text-black selection:bg-gray-200">
  
  <!-- Hero Headline -->
  <div class="mb-32 md:mb-48 max-w-4xl">
    <h1 class="text-5xl md:text-7xl lg:text-8xl leading-[1.05] font-normal tracking-tight">
      First-principles investing in U.S. housing.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-48 md:mb-64 relative -mx-6 md:-mx-16 lg:-mx-24">
    <div bind:this={carousel} class="flex gap-6 md:gap-12 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-6 md:px-16 lg:px-24">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-40 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-new-build-to-rent-community-with-contemp-1765733828669-1.webp" alt="Build-to-Rent Community" class="w-full h-[450px] md:h-[650px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="/generated/image-modern-single-family-rental-home-with-cl-1765733826118-0.webp" alt="Single-Family Rental Portfolio" class="w-full h-[450px] md:h-[650px] object-cover" />
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-40 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-modern-residential-construction-site-wit-1765733830793-2.webp" alt="Homebuilding Operations" class="w-full h-[450px] md:h-[650px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-40 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-upscale-residential-neighborhood-with-we-1765733832830-3.webp" alt="Quality Housing Stock" class="w-full h-[450px] md:h-[650px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Investment Focus -->
  <div class="mb-48 md:mb-64">
    <div class="mb-12 text-sm text-gray-400 tracking-wide">INVESTMENT FOCUS</div>
    <div class="max-w-3xl">
      <p class="text-3xl md:text-5xl lg:text-6xl leading-[1.15] font-normal tracking-tight text-gray-900">
        Single-family rentals, build-to-rent communities, and homebuilding across high-growth U.S. markets.
      </p>
    </div>
  </div>

  <!-- Investment Insights -->
  <div class="mb-48 md:mb-64">
    <div class="flex justify-between items-end mb-16">
      <div class="text-sm text-gray-400 tracking-wide">INSIGHTS</div>
      <a href="/" class="text-sm hover:opacity-50 transition-opacity">View all</a>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-12 md:gap-16">
      {#each insights as item}
        <article class="group cursor-pointer">
          <div class="overflow-hidden mb-6">
            <img src={item.image} alt={item.title} class="w-full aspect-[4/3] object-cover group-hover:scale-105 transition-transform duration-700" />
          </div>
          <h3 class="text-xl md:text-2xl leading-snug group-hover:opacity-50 transition-opacity">{item.title}</h3>
        </article>
      {/each}
    </div>
  </div>

  <!-- Portfolio -->
  <div class="mb-48 md:mb-64">
    <div class="mb-16 text-sm text-gray-400 tracking-wide">PORTFOLIO</div>
    <div class="flex flex-col gap-8">
      {#each portfolioCompanies.filter(c => c.highlight) as company}
        <a href="/" class="group block">
          <h3 class="text-4xl md:text-6xl lg:text-7xl font-normal leading-tight group-hover:opacity-50 transition-opacity">
            {company.name}
          </h3>
        </a>
      {/each}
    </div>
  </div>

  <!-- Investor Relations -->
  <div id="contact" class="mb-48 md:mb-64">
    <div class="mb-12 text-sm text-gray-400 tracking-wide">INVESTOR RELATIONS</div>
    <div class="max-w-2xl">
      <p class="text-2xl md:text-3xl leading-relaxed mb-12 text-gray-600">
        We partner with institutional investors and family offices seeking market-cycle resilient returns in U.S. housing.
      </p>
      <a href="mailto:investors@sidegate.com" class="inline-block text-lg hover:opacity-50 transition-opacity">
        investors@sidegate.com
      </a>
    </div>
  </div>

  <!-- Footer -->
  <footer class="pt-32 border-t border-gray-200">
    <div class="flex flex-col md:flex-row justify-between gap-16 mb-20">
      <!-- Logo -->
      <div>
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor"/>
        </svg>
      </div>

      <!-- Links -->
      <div class="flex flex-col md:flex-row gap-12 md:gap-20 text-sm">
        <div class="space-y-3 text-gray-600">
          <a href="/" class="block hover:text-black transition-colors">About</a>
          <a href="/" class="block hover:text-black transition-colors">Portfolio</a>
          <a href="/" class="block hover:text-black transition-colors">Insights</a>
        </div>
        <div class="space-y-3 text-gray-600">
          <a href="/" class="block hover:text-black transition-colors">Investors</a>
          <a href="/" class="block hover:text-black transition-colors">Careers</a>
          <a href="/" class="block hover:text-black transition-colors">Contact</a>
        </div>
      </div>
    </div>

    <!-- Bottom -->
    <div class="py-8 flex flex-col md:flex-row justify-between items-start md:items-center text-xs text-gray-400 gap-6">
      <div>© Sidegate 2025</div>
      
      <div class="flex gap-8">
        <a href="/" class="hover:text-black transition-colors">LinkedIn</a>
        <a href="/" class="hover:text-black transition-colors">Twitter</a>
      </div>
    </div>
  </footer>

</main>

