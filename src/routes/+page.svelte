<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import Section from "$lib/components/Section.svelte";
  
  const disciplines = [
    "Growth Strategy",
    "Performance Marketing",
    "Conversion Optimization",
    "Analytics & Attribution",
    "Content Marketing"
  ];

  const news = [
    {
      date: "January 2025",
      title: "SaaS Startup Achieves 312% User Growth in 6 Months",
      image: "/generated/image-saas-company-team-looking-at-user-growth-1765717782791-9.webp"
    },
    {
      date: "December 2024",
      title: "E-commerce Client Hits $2M ARR with 4.2x ROAS",
      image: "/generated/image-e-commerce-business-owner-reviewing-posi-1765717780530-8.webp"
    },
    {
      date: "November 2024",
      title: "B2B Company Doubles Pipeline with Transparent Attribution Model",
      image: "/generated/image-startup-founder-celebrating-growth-miles-1765717778193-7.webp"
    }
  ];

  const projects = [
    { name: "FinTech Startup", desc: "312% user growth in 6 months", highlight: true },
    { name: "E-commerce Brand", desc: "4.2x ROAS, $2M ARR", highlight: true },
    { name: "B2B SaaS Company", desc: "Doubled pipeline in 90 days", highlight: true },
    { name: "DTC Health Brand", desc: "Reduced CAC by 47%", highlight: false },
    { name: "EdTech Platform", desc: "3x organic traffic, 2.1x conversions", highlight: false },
    { name: "Mobile App Startup", desc: "From 0 to 50K users in 4 months", highlight: false },
    { name: "B2B Services", desc: "Generated $1.2M pipeline", highlight: false },
    { name: "Subscription Box", desc: "85% retention rate achieved", highlight: false },
    { name: "SaaS Analytics Tool", desc: "Scaled to 100 enterprise clients", highlight: true }
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
      Frank transforms business growth through candid, metric-driven strategies that compound results over time.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-32 relative -mx-5 md:-mx-10">
    <div bind:this={carousel} class="flex gap-4 md:gap-8 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-5 md:px-10">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-team-collaboration-session-with-charts-a-1765717764817-1.webp" alt="Team Strategy Session" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="/generated/image-marketing-founder-jason-reviewing-analyt-1765717762237-0.webp" alt="Metric-Driven Growth" class="w-full h-[400px] md:h-[600px] object-cover" />
        <div class="mt-4">
          <h3 class="text-lg font-medium">Metric-Driven Growth</h3>
          <p class="text-gray-500 text-lg">No fluff. No buzzwords. Just transparent results.</p>
        </div>
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-close-up-of-hands-pointing-at-growth-met-1765717767042-2.webp" alt="Analytics Review" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 grayscale transition-all hover:grayscale-0 hover:opacity-100">
        <img src="/generated/image-marketing-team-presenting-results-to-hap-1765717769366-3.webp" alt="Client Results" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Services -->
  <Section label="Services">
    <div class="flex flex-col border-t border-gray-200">
      {#each disciplines as discipline}
        <a href="/" class="py-6 border-b border-gray-200 text-3xl md:text-4xl lg:text-5xl font-normal hover:text-gray-500 transition-colors block">
          {discipline}
        </a>
      {/each}
    </div>
  </Section>

  <!-- Case Studies -->
  <Section label="Case Studies" link="/" linkText="All results">
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

  <!-- Approach -->
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-20 py-20 md:py-32">
    <div>
      <img src="/generated/image-founder-working-on-strategy-document-wit-1765717771525-4.webp" alt="Transparent Approach" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Transparent Approach</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        No agency fluff. No buzzwords. We show you exactly what we're doing, why we're doing it, and what results to expect. Every strategy backed by data.
      </p>
    </div>
    <div>
      <img src="/generated/image-dashboard-showing-upward-trending-graphs-1765717773728-5.webp" alt="Metric-Driven Results" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Metric-Driven Results</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        We measure everything. Clear before-and-after metrics, transparent ROI tracking, and honest reporting. Your growth compounds when you know what's working.
      </p>
    </div>
  </div>

  <!-- Client Results -->
  <Section label="Client Results">
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
        → <span class="group-hover:translate-x-1 transition-transform">See all client results</span>
      </a>
    </div>
  </Section>

  <!-- Get in touch -->
  <div class="py-20 md:py-32">
    <div class="max-w-xl">
      <img src="/generated/image-jason-shafton-confident-marketing-founde-1765717776044-6.webp" alt="Jason Shafton" class="w-full aspect-[3/2] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Ready for transparent growth?</h3>
      <p class="text-gray-500 text-lg mb-6">
        Tired of agency buzzwords and vague promises? Let's talk about real metrics and measurable results. Book a candid conversation with Jason.
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
        <svg class="h-8 w-auto" viewBox="0 0 745.52 203.47" xmlns="http://www.w3.org/2000/svg">
          <path fill="currentColor" d="M0,200.15V6.31h128.77v33.51H41.54v47.08h68.67v32.4H41.54v80.86H0Z"/>
          <path fill="currentColor" d="M127.79,200.15V60.59h36.83l3.6,25.48c3.69-5.91,8.03-10.98,13.01-15.23,4.98-4.25,10.71-7.57,17.17-9.97,6.46-2.4,13.66-3.6,21.6-3.6v44.03h-14.12c-5.54,0-10.52.6-14.95,1.8-4.43,1.2-8.31,3.18-11.63,5.95-3.32,2.77-5.82,6.51-7.48,11.21-1.66,4.71-2.49,10.57-2.49,17.58v62.31h-41.54Z"/>
          <path fill="currentColor" d="M273.89,203.47c-11.45,0-21-1.9-28.66-5.68-7.66-3.78-13.29-8.81-16.89-15.09-3.6-6.27-5.4-13.29-5.4-21.05s2.08-15.46,6.23-22.01c4.15-6.55,10.61-11.67,19.38-15.37,8.77-3.69,20.08-5.54,33.92-5.54h33.51c0-6.27-.79-11.49-2.35-15.65-1.57-4.15-4.11-7.24-7.62-9.28-3.51-2.03-8.31-3.05-14.4-3.05-6.46,0-11.91,1.34-16.34,4.02-4.43,2.68-7.2,6.78-8.31,12.32h-39.88c.92-9.97,4.15-18.64,9.69-26.03,5.54-7.38,13.06-13.2,22.57-17.45,9.51-4.24,20.35-6.37,32.54-6.37,13.29,0,24.83,2.12,34.61,6.37,9.78,4.25,17.4,10.57,22.85,18.97,5.44,8.4,8.17,18.79,8.17,31.15v86.4h-34.61l-4.98-20.21c-2.03,3.51-4.43,6.69-7.2,9.55-2.77,2.86-6,5.36-9.69,7.48-3.69,2.12-7.75,3.74-12.18,4.85-4.43,1.11-9.42,1.66-14.95,1.66ZM284.42,171.91c4.24,0,8.03-.74,11.35-2.22,3.32-1.48,6.23-3.5,8.72-6.09,2.49-2.58,4.52-5.58,6.09-9,1.57-3.41,2.72-7.24,3.46-11.49h-26.86c-4.62,0-8.49.6-11.63,1.8-3.14,1.2-5.4,2.96-6.79,5.26-1.38,2.31-2.08,4.85-2.08,7.62,0,3.14.78,5.72,2.35,7.75,1.57,2.03,3.69,3.6,6.37,4.71,2.67,1.11,5.68,1.66,9,1.66Z"/>
          <path fill="currentColor" d="M377.01,200.15V60.59h36.28l3.05,22.15c4.06-7.57,10.01-13.71,17.86-18.42,7.84-4.71,17.31-7.06,28.38-7.06,11.63,0,21.41,2.49,29.35,7.48,7.94,4.98,13.98,12.14,18.14,21.46,4.15,9.32,6.23,20.82,6.23,34.48v79.47h-41.54v-75.88c0-10.34-2.12-18.28-6.37-23.81-4.25-5.54-10.99-8.31-20.21-8.31-5.91,0-11.08,1.34-15.51,4.02-4.43,2.68-7.89,6.46-10.38,11.35-2.49,4.89-3.74,10.94-3.74,18.14v74.49h-41.54Z"/>
          <path fill="currentColor" d="M535.63,200.15V.77h41.54v199.38h-41.54ZM628.4,200.15l-57.32-76.43,51.23-63.14h49.01l-69.23,80.86v-33.51l77.81,92.21h-51.51Z"/>
          <g>
            <circle fill="currentColor" cx="711.71" cy="37.59" r="12.31"/>
            <path fill="currentColor" d="M701.44,8.35c-1.21,2.75-1.82,5.41-1.81,7.99,0,2.57.49,5.04,1.45,7.39.96,2.35,2.32,4.52,4.09,6.52,1.76,1.99,3.91,3.83,6.46,5.53l7.67-17.4c1.32-2.99,2.04-5.67,2.16-8.05.12-2.38-.37-4.34-1.47-5.9-1.1-1.56-2.55-2.73-4.34-3.52-2.04-.9-3.93-1.13-5.7-.69-1.76.43-3.39,1.36-4.87,2.78-1.48,1.42-2.7,3.2-3.65,5.36Z"/>
            <path fill="currentColor" d="M731.89,14.07c-2.99.33-5.59,1.14-7.82,2.44-2.22,1.3-4.11,2.95-5.67,4.96-1.55,2.01-2.75,4.28-3.59,6.8-.84,2.52-1.36,5.31-1.55,8.36l18.9-2.08c3.25-.36,5.93-1.08,8.05-2.17,2.12-1.09,3.57-2.5,4.37-4.23.8-1.73,1.09-3.57.87-5.52-.24-2.21-.99-3.97-2.26-5.28-1.26-1.31-2.88-2.25-4.85-2.82-1.97-.57-4.12-.73-6.46-.47Z"/>
            <path fill="currentColor" d="M742.17,43.34c-1.77-2.43-3.77-4.28-6.01-5.57-2.23-1.28-4.61-2.1-7.13-2.44-2.52-.35-5.08-.25-7.69.28-2.61.53-5.28,1.47-8.02,2.82l11.22,15.36c1.93,2.64,3.89,4.6,5.89,5.9,2,1.29,3.95,1.85,5.84,1.68,1.9-.17,3.64-.84,5.22-1.99,1.8-1.31,2.95-2.84,3.45-4.58.51-1.74.52-3.61.03-5.61-.48-1.99-1.42-3.94-2.81-5.84Z"/>
            <path fill="currentColor" d="M721.97,66.84c1.21-2.75,1.82-5.41,1.81-7.99,0-2.57-.49-5.04-1.45-7.39-.96-2.35-2.32-4.52-4.09-6.52-1.76-1.99-3.91-3.83-6.46-5.53l-7.67,17.4c-1.32,2.99-2.04,5.67-2.16,8.05-.12,2.38.37,4.34,1.47,5.9,1.1,1.56,2.55,2.73,4.34,3.52,2.04.9,3.93,1.13,5.7.69,1.76-.43,3.39-1.36,4.87-2.78,1.48-1.42,2.7-3.2,3.65-5.36Z"/>
            <path fill="currentColor" d="M691.53,61.11c2.99-.33,5.59-1.14,7.82-2.44,2.22-1.3,4.11-2.95,5.67-4.96,1.55-2.01,2.75-4.28,3.59-6.8.84-2.52,1.36-5.31,1.55-8.36l-18.9,2.08c-3.25.36-5.93,1.08-8.05,2.17-2.12,1.09-3.57,2.5-4.37,4.23-.8,1.73-1.09,3.57-.87,5.52.24,2.21.99,3.97,2.26,5.28,1.26,1.31,2.88,2.25,4.85,2.82,1.97.57,4.12.73,6.46.47Z"/>
            <path fill="currentColor" d="M681.25,31.85c1.77,2.43,3.77,4.28,6.01,5.57,2.23,1.28,4.61,2.1,7.13,2.44,2.52.35,5.08.25,7.69-.28,2.61-.53,5.28-1.47,8.02-2.82l-11.22-15.36c-1.93-2.64-3.89-4.6-5.89-5.9-2-1.29-3.95-1.85-5.84-1.68-1.9.17-3.64.84-5.22,1.99-1.8,1.31-2.95,2.84-3.45,4.58-.51,1.74-.52,3.61-.03,5.61.48,1.99,1.42,3.94,2.81,5.84Z"/>
          </g>
        </svg>
      </div>

      <!-- Links Columns -->
      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Company</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">About</a></li>
          <li><a href="/" class="hover:text-black">Approach</a></li>
          <li><a href="/" class="hover:text-black">Case Studies</a></li>
          <li><a href="/" class="hover:text-black">Founder</a></li>
          <li><a href="/" class="hover:text-black">Careers</a></li>
          <li><a href="/" class="hover:text-black">Contact</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Services</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Growth Strategy</a></li>
          <li><a href="/" class="hover:text-black">Performance Marketing</a></li>
          <li><a href="/" class="hover:text-black">Conversion Optimization</a></li>
          <li><a href="/" class="hover:text-black">Analytics & Attribution</a></li>
          <li><a href="/" class="hover:text-black">Content Marketing</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Resources</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Blog</a></li>
          <li><a href="/" class="hover:text-black">Metrics Guide</a></li>
          <li><a href="/" class="hover:text-black">Transparency Report</a></li>
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
      <div>© Frank 2025</div>
      
      <a href="/" class="flex items-center gap-1 hover:text-black">
        ↗ Book a Call
      </a>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Privacy Policy</a>
        <a href="/" class="hover:text-black">Terms of Service</a>
      </div>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">LinkedIn</a>
        <a href="/" class="hover:text-black">Twitter</a>
      </div>
    </div>
  </footer>

</main>

