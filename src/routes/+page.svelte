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

<main class="pt-32 pb-20 px-5 md:px-10 font-sans text-black selection:bg-gray-200">
  
  <!-- Hero Headline -->
  <div class="mb-20 md:mb-32 max-w-5xl">
    <h1 class="text-4xl md:text-6xl lg:text-7xl leading-[1.1] font-normal tracking-tight">
      Market-cycle resilient returns through first-principles investing and operational excellence in undersupplied housing.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-32 relative -mx-5 md:-mx-10">
    <div bind:this={carousel} class="flex gap-4 md:gap-8 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-5 md:px-10">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-new-build-to-rent-community-with-contemp-1765733828669-1.webp" alt="Build-to-Rent Community" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="/generated/image-modern-single-family-rental-home-with-cl-1765733826118-0.webp" alt="Single-Family Rental Portfolio" class="w-full h-[400px] md:h-[600px] object-cover" />
        <div class="mt-4">
          <h3 class="text-lg font-medium">Single-Family Rental Portfolio</h3>
          <p class="text-gray-500 text-lg">Operational excellence in undersupplied markets</p>
        </div>
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-modern-residential-construction-site-wit-1765733830793-2.webp" alt="Homebuilding Operations" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-upscale-residential-neighborhood-with-we-1765733832830-3.webp" alt="Quality Housing Stock" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Investment Strategies -->
  <Section label="Investment Strategies">
    <div class="flex flex-col border-t border-gray-200">
      {#each strategies as strategy}
        <a href="/" class="py-6 border-b border-gray-200 text-3xl md:text-4xl lg:text-5xl font-normal hover:text-gray-500 transition-colors block">
          {strategy}
        </a>
      {/each}
    </div>
  </Section>

  <!-- Investment Insights -->
  <Section label="Investment Insights" link="/" linkText="All insights">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each insights as item}
        <article class="group cursor-pointer">
          <div class="overflow-hidden mb-4">
            <img src={item.image} alt={item.title} class="w-full aspect-[4/3] object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <time class="text-gray-500 text-sm block mb-2">{item.date}</time>
          <h3 class="text-xl leading-snug group-hover:underline decoration-1 underline-offset-4">{item.title}</h3>
        </article>
      {/each}
    </div>
    
    <!-- Navigation Arrows -->
    <div class="flex justify-between mt-12 border-t border-transparent">
      <button class="hover:opacity-50 transition-opacity p-2 -ml-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
      </button>
      <button class="hover:opacity-50 transition-opacity p-2 -mr-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </button>
    </div>
  </Section>

  <!-- Investment Philosophy & Operational Excellence -->
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-20 py-20 md:py-32">
    <div>
      <img src="/generated/image-professional-investment-team-analyzing-d-1765733835001-4.webp" alt="Investment Philosophy" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">First-Principles Investing</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        We reject herd mentality and market noise, building proprietary views through direct research. Our contrarian approach values rigor over narratives, letting data and street-level insight guide decisions.
      </p>
    </div>
    <div>
      <img src="/generated/image-property-management-professional-inspect-1765733837035-5.webp" alt="Operational Excellence" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Operational Excellence</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        We treat operations as a craft, not a cost center. Consistent, risk-adjusted returns come from value-add operations that improve yields, reduce friction, and increase retention.
      </p>
    </div>
  </div>

  <!-- Portfolio Companies -->
  <Section label="Portfolio Companies">
    <div class="flex flex-col gap-2">
      {#each portfolioCompanies as company}
        <a href="/" class="group block">
          <h3 class="text-3xl md:text-5xl lg:text-6xl font-normal leading-tight">
            <span class="group-hover:underline decoration-1 underline-offset-8">{company.name}</span>
            {#if company.desc}
              <span class="text-gray-300 ml-2 group-hover:text-gray-400 transition-colors">{company.desc}</span>
            {/if}
          </h3>
        </a>
      {/each}
      
      <a href="/" class="inline-flex items-center gap-2 text-lg text-gray-500 mt-12 hover:text-black transition-colors group">
        → <span class="group-hover:translate-x-1 transition-transform">View full portfolio</span>
      </a>
    </div>
  </Section>

  <!-- Investor Relations -->
  <div id="contact" class="py-20 md:py-32">
    <div class="max-w-xl">
      <img src="/generated/image-confident-institutional-investors-in-bus-1765733839114-6.webp" alt="Investor Relations" class="w-full aspect-[3/2] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Investor Relations</h3>
      <p class="text-gray-500 text-lg mb-6">
        We partner with institutional investors and family offices seeking housing alpha through operational execution depth. Contact us to learn more about our investment strategies.
      </p>
      <a href="mailto:investors@sidegate.com" class="inline-flex items-center gap-2 px-6 py-3 border border-gray-200 hover:bg-black hover:text-white hover:border-black transition-colors text-sm font-medium">
        Contact Investor Relations →
      </a>
    </div>
  </div>

  <!-- Footer -->
  <footer class="pt-20 border-t border-gray-200">
    <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-4">
      <!-- Logo Column -->
      <div class="col-span-1 md:col-span-2">
        <svg width="40" height="40" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor"/>
        </svg>
      </div>

      <!-- Links Columns -->
      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Company</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">About</a></li>
          <li><a href="/" class="hover:text-black">Team</a></li>
          <li><a href="/" class="hover:text-black">Philosophy</a></li>
          <li><a href="/" class="hover:text-black">Portfolio</a></li>
          <li><a href="/" class="hover:text-black">Insights</a></li>
          <li><a href="/" class="hover:text-black">Careers</a></li>
          <li><a href="/" class="hover:text-black">Contact</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Strategies</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Single-Family Rentals</a></li>
          <li><a href="/" class="hover:text-black">Build-to-Rent</a></li>
          <li><a href="/" class="hover:text-black">Homebuilding</a></li>
          <li><a href="/" class="hover:text-black">Value-Add Operations</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Investors</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Investor Relations</a></li>
          <li><a href="/" class="hover:text-black">Performance</a></li>
          <li><a href="/" class="hover:text-black">Reports</a></li>
        </ul>
      </div>

      <!-- Contact -->
      <div class="col-span-1 md:col-span-4 flex flex-col justify-end">
        <div class="text-sm text-gray-600">
          <p class="mb-2">Institutional Investors</p>
          <a href="mailto:investors@sidegate.com" class="text-black hover:opacity-70">investors@sidegate.com</a>
        </div>
      </div>
    </div>

    <!-- Bottom Footer -->
    <div class="mt-20 py-8 flex flex-col md:flex-row justify-between items-start md:items-center text-xs text-gray-500 gap-4">
      <div>© Sidegate 2025</div>
      
      <a href="/" class="flex items-center gap-1 hover:text-black">
        ↗ Careers
      </a>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Privacy Policy</a>
        <a href="/" class="hover:text-black">Terms of Service</a>
        <a href="/" class="hover:text-black">Legal</a>
      </div>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">LinkedIn</a>
        <a href="/" class="hover:text-black">Twitter</a>
      </div>
    </div>
  </footer>

</main>

