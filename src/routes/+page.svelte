<script lang="ts">
	// Icons
	const ArrowDown = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-arrow-down"><path d="M12 5v14"/><path d="m19 12-7 7-7-7"/></svg>`;
	const ArrowUpRight = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-arrow-up-right"><path d="M7 7h10v10"/><path d="M7 17 17 7"/></svg>`;
	
	// Security Icons
	const IconGear = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12.22 2h-.44a2 2 0 0 0-2 2v.18a2 2 0 0 1-1 1.73l-.43.25a2 2 0 0 1-2 0l-.15-.08a2 2 0 0 0-2.73.73l-.22.38a2 2 0 0 0 .73 2.73l.15.1a2 2 0 0 1 1 1.72v.51a2 2 0 0 1-1 1.74l-.15.09a2 2 0 0 0-.73 2.73l.22.38a2 2 0 0 0 2.73.73l.15-.08a2 2 0 0 1 2 0l.43.25a2 2 0 0 1 1 1.73V20a2 2 0 0 0 2 2h.44a2 2 0 0 0 2-2v-.18a2 2 0 0 1 1-1.73l.43-.25a2 2 0 0 1 2 0l.15.08a2 2 0 0 0 2.73-.73l.22-.39a2 2 0 0 0-.73-2.73l-.15-.1a2 2 0 0 1-1-1.72v-.51a2 2 0 0 1 1-1.74l.15-.09a2 2 0 0 0 .73-2.73l-.22-.38a2 2 0 0 0-2.73-.73l-.15.08a2 2 0 0 1-2 0l-.43-.25a2 2 0 0 1-1-1.73V4a2 2 0 0 0-2-2z"/><circle cx="12" cy="12" r="3"/></svg>`;
	const IconLock = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect width="18" height="11" x="3" y="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>`;
	const IconFile = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M15 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7Z"/><path d="M14 2v4a2 2 0 0 0 2 2h4"/></svg>`;
	const IconShield = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z"/></svg>`;
	const IconKey = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="7.5" cy="15.5" r="5.5"/><path d="m21 2-9.6 9.6"/><path d="m15.5 7.5 3 3L22 7l-3-3"/></svg>`;
	const IconAward = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="8" r="6"/><path d="M15.477 12.89 17 22l-5-3-5 3 1.523-9.11"/></svg>`;

	// Flow Icons (Refined)
	const Flow1 = `<svg width="60" height="60" viewBox="0 0 60 60" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="30" cy="30" r="8" fill="black"/><path d="M30 10v6M30 44v6M10 30h6M44 30h6M16 16l4 4M40 40l4 4M16 44l4-4M40 20l4-4"/></svg>`; // Sun/Gear
	const Flow2 = `<svg width="80" height="60" viewBox="0 0 80 60" fill="none" stroke="currentColor" stroke-width="1"><path d="M40 10 L65 20 L40 30 L15 20 Z" /><path d="M40 20 L65 30 L40 40 L15 30 Z" /><path d="M40 30 L65 40 L40 50 L15 40 Z" /><path d="M40 40 L65 50 L40 60 L15 50 Z" /></svg>`; // Layers
	const Flow3 = `<svg width="60" height="60" viewBox="0 0 60 60" fill="currentColor"><circle cx="15" cy="15" r="1.5"/><circle cx="25" cy="15" r="1.5"/><circle cx="35" cy="15" r="1.5"/><circle cx="45" cy="15" r="1.5"/><circle cx="15" cy="25" r="1.5"/><circle cx="25" cy="25" r="1.5"/><circle cx="35" cy="25" r="1.5"/><circle cx="45" cy="25" r="1.5"/><circle cx="15" cy="35" r="1.5"/><circle cx="25" cy="35" r="1.5"/><circle cx="35" cy="35" r="1.5"/><circle cx="45" cy="35" r="1.5"/><circle cx="15" cy="45" r="1.5"/><circle cx="25" cy="45" r="1.5"/><circle cx="35" cy="45" r="1.5"/><circle cx="45" cy="45" r="1.5"/><line x1="55" y1="10" x2="55" y2="50" stroke="currentColor" stroke-width="1"/></svg>`; // Grid
	const Flow4 = `<svg width="80" height="60" viewBox="0 0 80 60" fill="none" stroke="currentColor" stroke-width="1"><circle cx="20" cy="40" r="1.5" fill="currentColor"/><circle cx="30" cy="30" r="1.5" fill="currentColor"/><circle cx="40" cy="35" r="1.5" fill="currentColor"/><circle cx="50" cy="20" r="1.5" fill="currentColor"/><circle cx="60" cy="25" r="1.5" fill="currentColor"/><circle cx="35" cy="15" r="1.5" fill="currentColor"/><circle cx="25" cy="50" r="1.5" fill="currentColor"/><line x1="20" y1="40" x2="30" y2="30"/><line x1="30" y1="30" x2="40" y2="35"/><line x1="40" y1="35" x2="50" y2="20"/><line x1="50" y1="20" x2="60" y2="25"/><line x1="30" y1="30" x2="35" y2="15"/></svg>`; // Scatter
	const Flow5 = `<svg width="60" height="50" viewBox="0 0 60 50" fill="none" stroke="currentColor" stroke-width="1"><path d="M15 10 L20 15 L30 5"/><circle cx="40" cy="10" r="1.5" fill="currentColor"/><circle cx="45" cy="10" r="1.5" fill="currentColor"/><circle cx="50" cy="10" r="1.5" fill="currentColor"/><path d="M15 25 L20 30 L30 20"/><circle cx="40" cy="25" r="1.5" fill="currentColor"/><circle cx="45" cy="25" r="1.5" fill="currentColor"/><circle cx="50" cy="25" r="1.5" fill="currentColor"/><path d="M15 40 L20 45 L30 35"/><circle cx="40" cy="40" r="1.5" fill="currentColor"/><circle cx="45" cy="40" r="1.5" fill="currentColor"/><circle cx="50" cy="40" r="1.5" fill="currentColor"/></svg>`; // Checklist
	const Flow6 = `<svg width="60" height="60" viewBox="0 0 60 60" fill="currentColor"><circle cx="30" cy="10" r="1.5"/><circle cx="38" cy="18" r="1.5"/><circle cx="22" cy="18" r="1.5"/><circle cx="46" cy="26" r="1.5"/><circle cx="30" cy="26" r="1.5"/><circle cx="14" cy="26" r="1.5"/><circle cx="54" cy="34" r="1.5"/><circle cx="38" cy="34" r="1.5"/><circle cx="22" cy="34" r="1.5"/><circle cx="6" cy="34" r="1.5"/><circle cx="46" cy="42" r="1.5"/><circle cx="30" cy="42" r="1.5"/><circle cx="14" cy="42" r="1.5"/><circle cx="38" cy="50" r="1.5"/><circle cx="22" cy="50" r="1.5"/><circle cx="30" cy="58" r="1.5"/></svg>`; // Diamond Grid

</script>

<main class="w-full overflow-x-hidden">
	<!-- Hero Section -->
	<section class="relative min-h-[90vh] flex flex-col justify-between px-6 py-6 md:px-12 md:py-8 overflow-hidden">
		
		<!-- Background Image -->
		<div class="absolute inset-0 w-full h-full">
			<img src="/uploaded/1767993607629-nwtltw6.png" alt="" class="w-full h-full object-cover object-bottom" />
		</div>
		
		<!-- Geometric Line Overlay -->
		<svg class="absolute inset-0 w-full h-full pointer-events-none opacity-10" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080" preserveAspectRatio="xMidYMid slice">
			<path d="M 800 0 Q 1200 400 800 800 Q 400 1200 800 1600" stroke="white" stroke-width="1" fill="none" opacity="0.3"/>
			<path d="M 1000 0 Q 1400 400 1000 800 Q 600 1200 1000 1600" stroke="white" stroke-width="1" fill="none" opacity="0.3"/>
			<path d="M 1200 0 Q 1600 400 1200 800 Q 800 1200 1200 1600" stroke="white" stroke-width="1" fill="none" opacity="0.3"/>
			<line x1="0" y1="500" x2="2000" y2="500" stroke="white" stroke-width="0.5" opacity="0.2"/>
			<line x1="0" y1="700" x2="2000" y2="700" stroke="white" stroke-width="0.5" opacity="0.2"/>
		</svg>

		<!-- Header -->
		<header class="flex justify-between items-start z-20">
			<div class="flex items-center gap-2 text-white">
				<span class="text-xl font-light tracking-wide">Mercator</span>
			</div>
			<a href="#" class="text-white text-sm hover:opacity-80 transition">Login</a>
		</header>

		<!-- Main Content -->
		<div class="flex-grow flex flex-col justify-center max-w-4xl z-20">
			<h1 class="text-3xl md:text-5xl lg:text-6xl font-sans text-white leading-[1.1] mb-12 mr-12 md:mr-24">
				Transforming legacy supply chains into intelligent, responsive systems.
			</h1>
			
			<div class="space-y-6 text-white/90 text-sm md:text-base leading-relaxed max-w-xl">
				<p class="font-medium">
					Our team spent over a decade leading groundbreaking AI efforts across Google. Since then, we've immersed ourselves in retail, co-developing intelligence with our favorite brands to address their most pressing challenges.
				</p>
			</div>

			<a href="#" class="inline-block mt-8 bg-white/20 backdrop-blur-md text-white text-sm font-medium px-3 py-2.5 rounded-full hover:bg-white/30 transition border border-white/30">
				Get started
			</a>
		</div>
	</section>

	<!-- How We Do It Section -->
	<section class="px-6 py-12 md:px-12 md:py-20">
		<div class="flex items-center gap-3 mb-8 md:mb-12">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">How we do it</span>
		</div>

		<h3 class="text-xl md:text-3xl font-mono max-w-3xl mb-16 leading-relaxed">
			Retail is leaking $1.7T annually due to manual supply chains.<br class="hidden md:block" />
			We automate the millions of decisions that leave money on the table.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
			<!-- Card 1 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="/generated/image-close-up-of-hands-analyzing-data-on-a-ta-1767978696212-1.webp" alt="Extract Constraints" class="w-full h-full object-cover transition duration-500" style="filter: grayscale(100%) sepia(20%) hue-rotate(180deg) saturate(150%) brightness(0.9);" />
					<div class="absolute inset-0 bg-blue-950/10 group-hover:bg-transparent transition duration-500"></div>
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">1</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Extract Constraints</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Mercator captures evolving constraints from emails and communications—vendor lead times, tariffs, promotions—that traditional tools miss.
				</p>
			</div>

			<!-- Card 2 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="/generated/image-supply-chain-planner-working-at-desk-wit-1767978698885-2.webp" alt="Orchestrate AI Agents" class="w-full h-full object-cover transition duration-500" style="filter: grayscale(100%) sepia(20%) hue-rotate(180deg) saturate(150%) brightness(0.9);" />
					<div class="absolute inset-0 bg-blue-950/10 group-hover:bg-transparent transition duration-500"></div>
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">2</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Orchestrate AI Agents</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					AI agents learn your company-specific playbooks and workflows, executing supply chain decisions better than humans can manually.
				</p>
			</div>

			<!-- Card 3 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="/generated/image-retail-store-floor-with-customers-shoppi-1767978701634-3.webp" alt="Real-Time Decisions" class="w-full h-full object-cover transition duration-500" style="filter: grayscale(100%) sepia(20%) hue-rotate(180deg) saturate(150%) brightness(0.9);" />
					<div class="absolute inset-0 bg-blue-950/10 group-hover:bg-transparent transition duration-500"></div>
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">3</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Real-Time Decisions</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Move from static planning to real-time action. Mercator reflects dynamic reality and recommends actions with confidence scores and revenue impact.
				</p>
			</div>

			<!-- Card 4 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="/generated/image-business-analytics-dashboard-on-screen-s-1767978704308-4.webp" alt="Drive Revenue" class="w-full h-full object-cover transition duration-500" style="filter: grayscale(100%) sepia(20%) hue-rotate(180deg) saturate(150%) brightness(0.9);" />
					<div class="absolute inset-0 bg-blue-950/10 group-hover:bg-transparent transition duration-500"></div>
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">4</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2 blur-reveal-delay-2">Drive Revenue</h4>
				<p class="text-sm text-gray-600 leading-relaxed blur-reveal-delay-3">
					Not just automation—enable what humans can't do today. Cuyana saw +6% incremental revenue in less than one month using Mercator.
				</p>
			</div>
		</div>
	</section>

	<!-- Credo Section -->
	<section class="px-6 py-12 md:px-12 md:py-24 bg-[#fdfbf7]">
		<div class="flex items-center gap-3 mb-12">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider blur-reveal">Our Story</span>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
			<div class="lg:col-span-5 lg:col-start-7 flex flex-col gap-8">
				<blockquote class="font-mono text-xl md:text-2xl leading-relaxed blur-reveal-delay-1">
					"Grace and I spent over a decade leading AI at Google—I worked on Gemini and TensorFlow, and Grace was tech lead on a supply chain moonshot at Google X. We saw firsthand how manual processes waste resources and leave money on the table. Retail is leaking $1.7T annually because planners are making millions of decisions with incomplete information. We're building Mercator to change that—AI agents that capture dynamic constraints, learn company playbooks, and automate decisions that humans simply can't make at scale. We're not just reducing costs. We're enabling revenue growth that was impossible before."
				</blockquote>

				<div class="flex items-center gap-4 mt-4">
					<img src="/generated/image-professional-asian-woman-in-her-30s-conf-1767978706790-5.webp" alt="Megha Malpani" class="w-16 h-16 object-cover grayscale" />
					<div>
						<div class="font-mono font-bold text-sm blur-reveal-delay-2">Megha Malpani</div>
						<div class="font-mono text-xs text-gray-500 blur-reveal-delay-3">Co-founder & CEO</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Flow Section -->
	<section class="px-6 py-12 md:px-12 md:py-20">
		<div class="flex items-center gap-3 mb-8">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider blur-reveal">How It Works</span>
		</div>

		<h3 class="text-xl md:text-2xl font-mono max-w-3xl mb-16 leading-relaxed blur-reveal-delay-1">
			10k SKUs × 10+ Checks × 10+ Levers = 1M+ manual choices.<br class="hidden md:block" />
			Mercator automates them all with AI agents that learn your playbooks.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 border-t border-l border-gray-200">
			<!-- Flow 1 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">1</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow1}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Connect</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Mercator integrates with your existing systems and communication channels, creating a unified view of your supply chain.
					</p>
				</div>
			</div>

			<!-- Flow 2 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">2</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow2}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Extract</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						AI extracts evolving constraints from emails, messages, and unstructured data—vendor delays, tariffs, promotions, margin priorities.
					</p>
				</div>
			</div>

			<!-- Flow 3 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">3</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow3}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Learn</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						AI agents learn your company-specific playbooks, workflows, and decision patterns to execute better than humans can manually.
					</p>
				</div>
			</div>

			<!-- Flow 4 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">4</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow4}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Recommend</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Mercator surfaces actionable recommendations with confidence scores and revenue impact projections—expedite orders, reallocate inventory, adjust MOQs.
					</p>
				</div>
			</div>

			<!-- Flow 5 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">5</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow5}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Execute</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Approve actions with one click or let agents execute automatically. Mercator handles the complexity while you maintain control.
					</p>
				</div>
			</div>

			<!-- Flow 6 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">6</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow6}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Optimize</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Continuous learning and real-time adjustments ensure your supply chain gets smarter over time, capturing more revenue with each decision.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Customers Section -->
	<section class="bg-[oklch(0.372_0.044_257.287)] text-white px-6 py-12 md:px-12 md:py-24">
		<div class="flex items-center gap-3 mb-12">
			<div class="w-1.5 h-1.5 bg-white rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Proven Results</span>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
			<div class="lg:col-span-6 lg:col-start-7 flex flex-col gap-8">
				<blockquote class="font-mono text-xl md:text-2xl leading-relaxed">
					"We piloted Mercator for less than one month and saw +6% incremental revenue using just one lever. As supply chain planners, we're constantly juggling thousands of SKUs and making decisions with incomplete information. Mercator captures the dynamic constraints we were missing—vendor delays, changing priorities, real-time demand signals—and surfaces actions we wouldn't have caught manually. The revenue impact was immediate and measurable. This is exactly what we needed to move from reactive planning to proactive optimization."
				</blockquote>

				<div class="flex items-center gap-4 mt-4">
					<img src="/generated/image-professional-woman-supply-chain-manager--1767978709444-6.webp" alt="Supply Chain Director" class="w-16 h-16 object-cover grayscale" />
					<div>
						<div class="font-mono font-bold text-sm">Supply Chain Director</div>
						<div class="font-mono text-xs text-white/80">Cuyana, ~$30M Revenue Apparel Brand</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Security Section -->
	<section class="px-6 py-12 md:px-12 md:py-24">
		<div class="flex items-center gap-3 mb-8">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Enterprise-Grade Security</span>
		</div>

		<h3 class="text-xl md:text-2xl font-mono max-w-3xl mb-16 leading-relaxed">
			Your supply chain data is your competitive advantage. Mercator is built with enterprise-grade security that retail brands and their partners trust. Your data stays private, encrypted, and fully under your control.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-12 gap-y-16">
			<!-- Item 1 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconGear}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Your Data,<br>Your Control</h4>
				<p class="text-xs text-gray-600 leading-relaxed blur-reveal-delay-3">
					Mercator never uses your supply chain data to train AI models. Optional Zero Data Retention ensures your inputs are not logged or stored. You control access, retention, and deletion at every stage.
				</p>
			</div>

			<!-- Item 2 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconLock}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Secure, Encrypted<br>Infrastructure</h4>
				<p class="text-xs text-gray-600 leading-relaxed blur-reveal-delay-3">
					All data is encrypted in transit and at rest (TLS 1.2+, AES-256) and processed on multi-region, highly available cloud infrastructure with continuous monitoring and redundancy.
				</p>
			</div>

			<!-- Item 3 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconFile}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Granular Retention &<br>Privacy Controls</h4>
				<p class="text-xs text-gray-600 leading-relaxed blur-reveal-delay-3">
					Retention and deletion follow GDPR/CCPA-aligned workflows. You control how long supply chain data is stored and can delete it at any time.
				</p>
			</div>

			<!-- Item 4 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconAward}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Independently<br>Audited Compliance</h4>
				<p class="text-xs text-gray-600 leading-relaxed blur-reveal-delay-3">
					SOC 2 Type II and ISO 27001 audited controls validate our commitments to security, availability, and confidentiality. Regular penetration testing ensures ongoing compliance.
				</p>
			</div>

			<!-- Item 5 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconKey}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Enterprise Access &<br>Threat Protection</h4>
				<p class="text-xs text-gray-600 leading-relaxed blur-reveal-delay-3">
					SSO and SCIM provisioning, MFA, and granular role-based access controls ensure alignment with your enterprise identity architecture. Continuous monitoring protects against threats.
				</p>
			</div>

			<!-- Item 6 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconShield}</div>
				<h4 class="font-mono font-bold text-sm mb-2 blur-reveal-delay-2">Built for Retail<br>Enterprise Standards</h4>
				<a href="#" class="inline-flex items-center gap-2 bg-black text-white text-xs font-mono py-2 px-4 mt-2 hover:bg-gray-800 transition blur-reveal-delay-3">
					Our security portal {@html ArrowUpRight}
				</a>
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-black text-white pt-16 pb-0 overflow-hidden">
		<!-- CTA Section -->
		<section class="px-6 py-20 md:py-32 text-center">
			<h2 class="text-2xl md:text-4xl font-mono mb-8">Ready to capture the revenue you're missing?</h2>
			<button class="bg-white text-black px-8 py-3 font-mono text-sm hover:bg-gray-100 transition">
				Book a demo
			</button>
		</section>
		<div class="px-6 md:px-12 mb-16 flex flex-col md:flex-row justify-between gap-12">
			<div class="text-xs font-mono text-gray-400">
				© Mercator Intelligence 2025
			</div>

			<div class="flex gap-16">
				<div class="flex flex-col gap-2">
					<a href="#" class="text-xs font-mono hover:text-gray-300">Resources</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Security</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Careers</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Privacy Policy</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Terms of Use</a>
				</div>
				<div class="flex flex-col gap-2">
					<a href="mailto:hello@mercatorintel.com" class="text-xs font-mono hover:text-gray-300">hello@mercatorintel.com</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Linkedin</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">x.com</a>
				</div>
			</div>
		</div>

		<!-- Big Logo -->
		<div class="relative w-full flex justify-center overflow-hidden z-10">
			<div class="text-[10vw] md:text-[12vw] leading-none font-black tracking-tighter text-white select-none relative blur-reveal-delay-2" style="font-family: 'Inter', sans-serif;">
				MERCATOR
				<!-- Dot texture overlay -->
				<div class="absolute inset-0 pointer-events-none" style="background-image: radial-gradient(circle, black 25%, transparent 25%); background-size: 6px 6px;"></div>
			</div>
		</div>
	</footer>
</main>

<style>
	:global(body) {
		background-color: #fdfbf7;
	}

	@keyframes blurReveal {
		from {
			filter: blur(10px);
			opacity: 0;
		}
		to {
			filter: blur(0);
			opacity: 1;
		}
	}

	.blur-reveal {
		animation: blurReveal 0.8s ease-out forwards;
	}

	.blur-reveal-delay-1 {
		animation: blurReveal 0.8s ease-out 0.1s forwards;
		opacity: 0;
	}

	.blur-reveal-delay-2 {
		animation: blurReveal 0.8s ease-out 0.2s forwards;
		opacity: 0;
	}

	.blur-reveal-delay-3 {
		animation: blurReveal 0.8s ease-out 0.3s forwards;
		opacity: 0;
	}

	.blur-reveal-delay-4 {
		animation: blurReveal 0.8s ease-out 0.4s forwards;
		opacity: 0;
	}

	.blur-reveal-delay-5 {
		animation: blurReveal 0.8s ease-out 0.5s forwards;
		opacity: 0;
	}

	.blur-reveal-delay-6 {
		animation: blurReveal 0.8s ease-out 0.6s forwards;
		opacity: 0;
	}
</style>