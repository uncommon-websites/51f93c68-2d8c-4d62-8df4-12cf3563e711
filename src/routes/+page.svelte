<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import Section from "$lib/components/Section.svelte";
  
  const disciplines = [
    "Structured Alpha Strategies",
    "Convertible Securities",
    "Options-Based Income",
    "Alternative Investments",
    "Risk-Managed Portfolios"
  ];

  const news = [
    {
      date: "15 January 2025",
      title: "Calamos Expands Alternative Investment Education Programs for RIA Partners",
      image: "/generated/image-professional-investment-conference-with--1766010892767-4.webp"
    },
    {
      date: "08 January 2025",
      title: "Structured Alpha Strategies Deliver Consistent Risk-Adjusted Returns in Volatile Markets",
      image: "/generated/image-modern-portfolio-management-team-collabo-1766010896196-5.webp"
    },
    {
      date: "03 January 2025",
      title: "Market Outlook 2025: Navigating Opportunities in Alternative Investments",
      image: "/generated/image-financial-data-visualization-on-large-sc-1766010899471-6.webp"
    }
  ];

  const projects = [
    { name: "Calamos Structured Alpha Fund", desc: "Equity exposure with downside protection", highlight: true },
    { name: "Convertible Opportunities Strategy", desc: "Asymmetric risk\/reward profiles", highlight: true },
    { name: "Options-Based Income Solutions", desc: "Systematic income generation", highlight: true },
    { name: "Global Alternative Income Fund", desc: "Putting the “square” back", highlight: false },
    { name: "Market Neutral Income Strategy", desc: "Low correlation to traditional markets", highlight: false },
    { name: "Phineus Long\/Short Fund", desc: "Active equity hedge strategy", highlight: false },
    { name: "Timpani Small Cap Growth", desc: "Growth with risk management", highlight: false },
    { name: "Convertible \& High Income Fund", desc: "Hybrid securities expertise", highlight: false },
    { name: "Hedged Equity Strategy", desc: "Protection in volatile markets", highlight: true }
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
      Calamos delivers institutional-grade alternative investments to individual investors through disciplined, risk-managed strategies.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-32 relative -mx-5 md:-mx-10">
    <div bind:this={carousel} class="flex gap-4 md:gap-8 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-5 md:px-10">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-investment-team-analyzing-market-data-on-1766010877978-1.webp" alt="Investment Analysis" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="/generated/image-professional-financial-advisor-meeting-w-1766010869475-0.webp" alt="Financial Advisory Partnership" class="w-full h-[400px] md:h-[600px] object-cover" />
        <div class="mt-4">
          <h3 class="text-lg font-medium">Partnering with Financial Advisors</h3>
          <p class="text-gray-500 text-lg">Empowering RIAs with institutional-grade alternatives</p>
        </div>
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-senior-financial-advisor-reviewing-portf-1766010884256-2.webp" alt="Client Advisory" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-ria-advisor-working-at-desk-with-financi-1766010888683-3.webp" alt="RIA Professional" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Investment Strategies -->
  <Section label="Investment Strategies">
    <div class="flex flex-col border-t border-gray-200">
      {#each disciplines as discipline}
        <a href="/" class="py-6 border-b border-gray-200 text-3xl md:text-4xl lg:text-5xl font-normal hover:text-gray-500 transition-colors block">
          {discipline}
        </a>
      {/each}
    </div>
  </Section>

  <!-- Market Insights -->
  <Section label="Market Insights" link="/" linkText="All insights">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each news as item}
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

  <!-- Our Approach & Legacy -->
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-20 py-20 md:py-32">
    <div>
      <img src="/generated/image-investment-professionals-in-strategy-mee-1766010903031-7.webp" alt="Our Investment Approach" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Disciplined Investment Approach</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        Our systematic process has been refined since 1977, combining rigorous risk management with institutional-grade research to deliver consistent results for investors.
      </p>
    </div>
    <div>
      <img src="/generated/image-distinguished-senior-executive-in-profes-1766010906314-8.webp" alt="Founder Legacy" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Military Discipline, Investment Excellence</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        Founded by Air Force veteran John P. Calamos Sr., our firm embodies military precision and discipline in every investment decision, democratizing sophisticated strategies for all investors.
      </p>
    </div>
  </div>

  <!-- Investment Solutions -->
  <Section label="Investment Solutions">
    <div class="flex flex-col gap-2">
      {#each projects as project}
        <a href="/" class="group block">
          <h3 class="text-3xl md:text-5xl lg:text-6xl font-normal leading-tight">
            <span class="group-hover:underline decoration-1 underline-offset-8">{project.name}</span>
            {#if project.desc}
              <span class="text-gray-300 ml-2 group-hover:text-gray-400 transition-colors">{project.desc}</span>
            {/if}
          </h3>
        </a>
      {/each}
      
      <a href="/" class="inline-flex items-center gap-2 text-lg text-gray-500 mt-12 hover:text-black transition-colors group">
        → <span class="group-hover:translate-x-1 transition-transform">Explore all investment solutions</span>
      </a>
    </div>
  </Section>

  <!-- Partner with Us -->
  <div class="py-20 md:py-32">
    <div class="max-w-xl">
      <img src="/generated/image-financial-advisor-presenting-to-small-gr-1766010909553-9.webp" alt="Partner with Calamos" class="w-full aspect-[3/2] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Partner with Calamos</h3>
      <p class="text-gray-500 text-lg mb-6">
        Join our network of financial advisors. Discover how Calamos can help you deliver institutional-grade alternatives to your clients.
      </p>
      <button class="w-10 h-10 border border-gray-200 flex items-center justify-center hover:bg-black hover:text-white transition-colors">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <line x1="4" y1="21" x2="4" y2="14"></line>
          <line x1="4" y1="10" x2="4" y2="3"></line>
          <line x1="12" y1="21" x2="12" y2="12"></line>
          <line x1="12" y1="8" x2="12" y2="3"></line>
          <line x1="20" y1="21" x2="20" y2="16"></line>
          <line x1="20" y1="12" x2="20" y2="3"></line>
          <line x1="1" y1="14" x2="7" y2="14"></line>
          <line x1="9" y1="8" x2="15" y2="8"></line>
          <line x1="17" y1="16" x2="23" y2="16"></line>
        </svg>
      </button>
    </div>
  </div>

  <!-- Footer -->
  <footer class="pt-20 border-t border-gray-200">
    <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-4">
      <!-- Logo Column -->
      <div class="col-span-1 md:col-span-2">
        <svg width="40" height="40" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M2 28L10 12L16 24L22 8L30 28" stroke="currentColor" stroke-width="2" stroke-linejoin="round" stroke-linecap="round"/>
        </svg>
      </div>

      <!-- Links Columns -->
      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">General</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">About us</a></li>
          <li><a href="/" class="hover:text-black">Leadership</a></li>
          <li><a href="/" class="hover:text-black">Investment team</a></li>
          <li><a href="/" class="hover:text-black">Market insights</a></li>
          <li><a href="/" class="hover:text-black">News & media</a></li>
          <li><a href="/" class="hover:text-black">Careers</a></li>
          <li><a href="/" class="hover:text-black">Contact</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Investment strategies</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Structured alpha</a></li>
          <li><a href="/" class="hover:text-black">Convertible securities</a></li>
          <li><a href="/" class="hover:text-black">Options-based income</a></li>
          <li><a href="/" class="hover:text-black">Alternative investments</a></li>
          <li><a href="/" class="hover:text-black">Risk-managed portfolios</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Resources</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Market outlook</a></li>
          <li><a href="/" class="hover:text-black">Research & commentary</a></li>
          <li><a href="/" class="hover:text-black">Educational resources</a></li>
          <li><a href="/" class="hover:text-black">Fund documents</a></li>
        </ul>
      </div>

      <!-- Search -->
      <div class="col-span-1 md:col-span-4 flex flex-col justify-end">
        <div class="border-b border-gray-200 flex justify-between items-center py-2">
          <input type="text" placeholder="Search" class="outline-none w-full text-sm placeholder-gray-400" />
          <span class="text-gray-400">+</span>
        </div>
      </div>
    </div>

    <!-- Bottom Footer -->
    <div class="mt-20 py-8 flex flex-col md:flex-row justify-between items-start md:items-center text-xs text-gray-500 gap-4">
      <div>© Calamos Investments 2025</div>
      
      <a href="/" class="flex items-center gap-1 hover:text-black">
        ↗ Current Openings
      </a>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Transparency Act</a>
        <a href="/" class="hover:text-black">Cookies & Tracking</a>
        <a href="/" class="hover:text-black">Legal Documents</a>
      </div>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Instagram</a>
        <a href="/" class="hover:text-black">Facebook</a>
        <a href="/" class="hover:text-black">LinkedIn</a>
      </div>
    </div>
  </footer>

</main>

