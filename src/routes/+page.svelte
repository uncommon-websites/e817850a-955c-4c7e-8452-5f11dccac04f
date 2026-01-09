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
	<section class="relative min-h-[90vh] flex flex-col justify-between px-6 py-6 md:px-12 md:py-8 bg-gradient-to-b from-[#6b6b6b] to-[#3a3a3a]">
		<!-- Header -->
		<header class="flex justify-between items-start z-20">
			<div class="font-mono text-sm tracking-widest font-bold flex items-center gap-2 text-white">
				<svg width="45" height="58" viewBox="0 0 90 115" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path fill-rule="evenodd" clip-rule="evenodd" d="M31.8701 9.95388L15.3109 19.4791L31.8819 29.0064L48.446 19.4812L31.8701 9.95388ZM53.2588 27.7795L36.6927 37.3058L36.6911 56.3603L53.2588 46.8319V27.7795ZM58.0696 55.1313L41.5014 64.66L58.072 74.187L74.6383 64.6605L58.0696 55.1313ZM79.4486 72.9601L62.883 82.4862V101.538L79.4486 92.0122V72.9601ZM53.2614 101.539V82.4864L36.6903 72.9591V92.012L53.2614 101.539ZM27.0694 56.3613L10.5003 46.8319V27.7788L27.0711 37.3058L27.0694 56.3613ZM27.0687 67.4269L4.48643 54.4394C2.25391 53.1554 0.878662 50.7828 0.878662 48.215V19.4801C0.878662 17.7684 1.79538 16.1867 3.28356 15.3307L28.2608 0.963381C30.4933 -0.320696 33.2439 -0.321154 35.4766 0.962171L60.474 15.3299C61.963 16.1857 62.8804 17.7679 62.8804 19.4801V46.8319L86.665 60.5111C88.1535 61.3671 89.0702 62.9489 89.0702 64.6607V93.3956C89.0702 95.9635 87.6948 98.3361 85.4621 99.62L60.4776 113.988C58.9894 114.843 57.1558 114.843 55.6673 113.988L30.6773 99.6202C28.4444 98.3365 27.0687 95.9635 27.0687 93.3954V67.4269Z" fill="white"/>
				</svg>
				<span>MERCATOR</span>
			</div>
		</header>

		<!-- Main Content -->
		<div class="flex-grow flex flex-col justify-center items-center relative mt-10 md:mt-0">
			<div class="w-full flex justify-between items-center absolute top-1/2 -translate-y-1/2 z-10 pointer-events-none px-4 md:px-16 lg:px-32">
				<h1 class="text-4xl md:text-7xl lg:text-8xl font-mono text-white opacity-90">Inventory</h1>
				<h1 class="text-4xl md:text-7xl lg:text-8xl font-mono text-white opacity-90">Reimagined</h1>
			</div>

			<!-- Image Container -->
			<div class="relative w-full max-w-lg aspect-square flex items-center justify-center z-0">
				<!-- Placeholder for Glass Cube -->
				<div class="w-64 h-64 md:w-80 md:h-80 relative">
					<img 
						src="/generated/image-modern-retail-warehouse-with-organized-i-1767978693395-0.webp" 
						alt="Modern retail warehouse with organized inventory" 
						class="w-full h-full object-cover shadow-2xl opacity-80"
						style="mask-image: radial-gradient(circle, black 40%, transparent 80%); -webkit-mask-image: radial-gradient(circle, black 40%, transparent 80%);"
					/>
					<!-- Glass Box Border Simulation -->
					<div class="absolute inset-0 border border-white/40 bg-white/5 backdrop-blur-[1px] shadow-2xl"></div>
					<div class="absolute inset-4 border border-white/20"></div>
				</div>
			</div>
		</div>

		<!-- Footer of Hero -->
		<div class="flex flex-col items-center gap-8 pb-10 z-20">
			<p class="text-center max-w-md text-sm md:text-base font-mono text-white/90 leading-relaxed">
				The first system of action for supply chain management.<br class="hidden md:block" />
				AI agents that automate decisions and drive revenue.
			</p>
			<div class="border border-white/30 rounded p-1 text-white">
				{@html ArrowDown}
			</div>
		</div>
	</section>

	<!-- Intro Section -->
	<section class="px-6 py-20 md:px-12 md:py-32 max-w-5xl mx-auto text-center">
		<h2 class="text-2xl md:text-4xl lg:text-5xl font-mono leading-tight md:leading-snug">
			Mercator automates supply chain decisions by extracting constraints 
			from communications and orchestrating AI agents—enabling retail brands 
			to capture revenue they're missing from manual planning.
		</h2>
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
					<img src="/generated/image-close-up-of-hands-analyzing-data-on-a-ta-1767978696212-1.webp" alt="Extract Constraints" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
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
					<img src="/generated/image-supply-chain-planner-working-at-desk-wit-1767978698885-2.webp" alt="Orchestrate AI Agents" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
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
					<img src="/generated/image-retail-store-floor-with-customers-shoppi-1767978701634-3.webp" alt="Real-Time Decisions" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
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
					<img src="/generated/image-business-analytics-dashboard-on-screen-s-1767978704308-4.webp" alt="Drive Revenue" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">4</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Drive Revenue</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Not just automation—enable what humans can't do today. Cuyana saw +6% incremental revenue in less than one month using Mercator.
				</p>
			</div>
		</div>
	</section>

	<!-- Credo Section -->
	<section class="px-6 py-12 md:px-12 md:py-24 bg-[#fdfbf7]">
		<div class="flex items-center gap-3 mb-12">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Our Story</span>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
			<div class="lg:col-span-5 lg:col-start-7 flex flex-col gap-8">
				<blockquote class="font-mono text-xl md:text-2xl leading-relaxed">
					"Grace and I spent over a decade leading AI at Google—I worked on Gemini and TensorFlow, and Grace was tech lead on a supply chain moonshot at Google X. We saw firsthand how manual processes waste resources and leave money on the table. Retail is leaking $1.7T annually because planners are making millions of decisions with incomplete information. We're building Mercator to change that—AI agents that capture dynamic constraints, learn company playbooks, and automate decisions that humans simply can't make at scale. We're not just reducing costs. We're enabling revenue growth that was impossible before."
				</blockquote>

				<div class="flex items-center gap-4 mt-4">
					<img src="/generated/image-professional-asian-woman-in-her-30s-conf-1767978706790-5.webp" alt="Megha Malpani" class="w-16 h-16 object-cover grayscale" />
					<div>
						<div class="font-mono font-bold text-sm">Megha Malpani</div>
						<div class="font-mono text-xs text-gray-500">Co-founder & CEO</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Flow Section -->
	<section class="px-6 py-12 md:px-12 md:py-20">
		<div class="flex items-center gap-3 mb-8">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">How It Works</span>
		</div>

		<h3 class="text-xl md:text-2xl font-mono max-w-3xl mb-16 leading-relaxed">
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
				<h4 class="font-mono font-bold text-sm mb-2">Your Data,<br>Your Control</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					Mercator never uses your supply chain data to train AI models. Optional Zero Data Retention ensures your inputs are not logged or stored. You control access, retention, and deletion at every stage.
				</p>
			</div>

			<!-- Item 2 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconLock}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Secure, Encrypted<br>Infrastructure</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					All data is encrypted in transit and at rest (TLS 1.2+, AES-256) and processed on multi-region, highly available cloud infrastructure with continuous monitoring and redundancy.
				</p>
			</div>

			<!-- Item 3 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconFile}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Granular Retention &<br>Privacy Controls</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					Retention and deletion follow GDPR/CCPA-aligned workflows. You control how long supply chain data is stored and can delete it at any time.
				</p>
			</div>

			<!-- Item 4 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconAward}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Independently<br>Audited Compliance</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					SOC 2 Type II and ISO 27001 audited controls validate our commitments to security, availability, and confidentiality. Regular penetration testing ensures ongoing compliance.
				</p>
			</div>

			<!-- Item 5 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconKey}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Enterprise Access &<br>Threat Protection</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					SSO and SCIM provisioning, MFA, and granular role-based access controls ensure alignment with your enterprise identity architecture. Continuous monitoring protects against threats.
				</p>
			</div>

			<!-- Item 6 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconShield}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Built for Retail<br>Enterprise Standards</h4>
				<a href="#" class="inline-flex items-center gap-2 bg-black text-white text-xs font-mono py-2 px-4 mt-2 hover:bg-gray-800 transition">
					Our security portal {@html ArrowUpRight}
				</a>
			</div>
		</div>
	</section>

	<!-- CTA Section -->
	<section class="px-6 py-20 md:py-32 text-center">
		<h2 class="text-2xl md:text-4xl font-mono mb-8">Ready to capture the revenue you're missing?</h2>
		<button class="bg-black text-white px-8 py-3 font-mono text-sm hover:bg-gray-800 transition">
			Book a demo
		</button>
	</section>

	<!-- Footer -->
	<footer class="bg-black text-white pt-16 pb-0 overflow-hidden">
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
		<div class="w-full flex justify-center overflow-hidden">
			<div class="text-[10vw] md:text-[12vw] leading-none font-black tracking-tighter text-white select-none relative" style="font-family: 'Inter', sans-serif;">
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
</style>

