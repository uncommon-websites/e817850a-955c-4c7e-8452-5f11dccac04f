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
	<section class="relative min-h-[90vh] flex flex-col justify-between px-6 py-6 md:px-12 md:py-8 bg-gradient-to-b from-[#a3a3a3] to-[#5e5e5e]">
		<!-- Header -->
		<header class="flex justify-between items-start z-20">
			<div class="font-mono text-xl tracking-widest font-bold flex items-center gap-1 text-white">
				AUCTOR
				<div class="h-4 w-4 bg-white/50 ml-1 inline-block align-middle"></div>
			</div>
		</header>

		<!-- Main Content -->
		<div class="flex-grow flex flex-col justify-center items-center relative mt-10 md:mt-0">
			<div class="w-full flex justify-between items-center absolute top-1/2 -translate-y-1/2 z-10 pointer-events-none px-4 md:px-16 lg:px-32">
				<h1 class="text-4xl md:text-7xl lg:text-8xl font-mono text-white opacity-90">Promises</h1>
				<h1 class="text-4xl md:text-7xl lg:text-8xl font-mono text-white opacity-90">Delivered</h1>
			</div>

			<!-- Image Container -->
			<div class="relative w-full max-w-lg aspect-square flex items-center justify-center z-0">
				<!-- Placeholder for Glass Cube -->
				<div class="w-64 h-64 md:w-80 md:h-80 relative">
					<img 
						src="https://images.unsplash.com/photo-1521791136064-7986c2920216?q=80&w=1000&auto=format&fit=crop" 
						alt="Handshake in glass cube" 
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
				The agentic operating system for modern professional<br class="hidden md:block" />
				services and system integrators.
			</p>
			<div class="border border-white/30 rounded p-1 text-white">
				{@html ArrowDown}
			</div>
		</div>
	</section>

	<!-- Intro Section -->
	<section class="px-6 py-20 md:px-12 md:py-32 max-w-5xl mx-auto text-center">
		<h2 class="text-2xl md:text-4xl lg:text-5xl font-mono leading-tight md:leading-snug">
			Auctor brings alignment and intelligence to software
			implementation, enabling every project to deliver its intended
			value with clarity and precision.
		</h2>
	</section>

	<!-- How We Do It Section -->
	<section class="px-6 py-12 md:px-12 md:py-20">
		<div class="flex items-center gap-3 mb-8 md:mb-12">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">How we do it</span>
		</div>

		<h3 class="text-xl md:text-3xl font-mono max-w-3xl mb-16 leading-relaxed">
			In order to reduce complexity and improve<br class="hidden md:block" />
			outcomes, we elevate every part of the journey.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
			<!-- Card 1 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="https://images.unsplash.com/photo-1605721911519-3dfeb3be25e7?q=80&w=600&auto=format&fit=crop" alt="Discovery" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">1</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">No more (re)discovery</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Stay in forward motion. Use Auctor to instantly capture and generate requirements the first time around. No more wasting cycles.
				</p>
			</div>

			<!-- Card 2 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="https://images.unsplash.com/photo-1518640467707-6811f4a6ab73?q=80&w=600&auto=format&fit=crop" alt="Aligned" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">2</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Aligned, every time</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					No more "he said, she said." Auctor keeps every conversation, artifact, and decision connected and traceable through go-live and beyond.
				</p>
			</div>

			<!-- Card 3 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="https://images.unsplash.com/photo-1542273917363-3b1817f69a2d?q=80&w=600&auto=format&fit=crop" alt="Knowledge" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">3</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Leverage rooted knowledge</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Auctor learns from your past projects and existing workflows, following best practices and helping every implementation move more efficiently.
				</p>
			</div>

			<!-- Card 4 -->
			<div class="group">
				<div class="relative aspect-square mb-6 overflow-hidden rounded-sm bg-gray-100">
					<img src="https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?q=80&w=600&auto=format&fit=crop" alt="Do more" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" />
					<div class="absolute top-4 left-4 w-8 h-8 bg-white/90 rounded-full flex items-center justify-center font-mono text-sm">4</div>
				</div>
				<h4 class="font-mono font-bold text-lg mb-2">Do more with less</h4>
				<p class="text-sm text-gray-600 leading-relaxed">
					Generate artifacts in hours instead of weeks. Auctor enables smaller teams to deliver faster and focus on outcomes with less overhead.
				</p>
			</div>
		</div>
	</section>

	<!-- Credo Section -->
	<section class="px-6 py-12 md:px-12 md:py-24 bg-[#fdfbf7]">
		<div class="flex items-center gap-3 mb-12">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Our Credo</span>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
			<div class="lg:col-span-5 lg:col-start-7 flex flex-col gap-8">
				<blockquote class="font-mono text-xl md:text-2xl leading-relaxed">
					"Our vision is to give every professional services organization the tools to focus on what matters most: advising customers, shaping outcomes, and driving real business change. We're building more than a product. Alongside industry experts, we're setting a new gold standard for services teams and redefining '<span class="italic">professional services automation</span>' through agentic delivery. We're building a future where technology amplifies expertise, where teams operate with clarity and efficiency, and where every implementation reaches its full potential."
				</blockquote>

				<div class="flex items-center gap-4 mt-4">
					<img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=200&auto=format&fit=crop" alt="Will Sun" class="w-16 h-16 object-cover grayscale" />
					<div>
						<div class="font-mono font-bold text-sm">Will Sun</div>
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
			<span class="font-mono text-xs uppercase tracking-wider">Flow</span>
		</div>

		<h3 class="text-xl md:text-2xl font-mono max-w-3xl mb-16 leading-relaxed">
			While every process and workflow is different, we use<br class="hidden md:block" />
			the following framework to ensure speed and quality.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 border-t border-l border-gray-200">
			<!-- Flow 1 -->
			<div class="border-r border-b border-gray-200 p-8 h-80 flex flex-col justify-between relative">
				<div class="absolute top-8 left-8 w-6 h-6 bg-black text-white rounded-full flex items-center justify-center font-mono text-xs">1</div>
				<div class="flex-grow flex items-center justify-center text-black">
					{@html Flow1}
				</div>
				<div>
					<h4 class="font-mono font-bold text-lg mb-2">Ingest</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Auctor ingests your institutional knowledge, builds a living knowledge base, and adapts to your workflows from day one.
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
					<h4 class="font-mono font-bold text-lg mb-2">Capture</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Discovery sessions, workshops, notes, and other unstructured data are captured automatically so nothing gets lost.
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
					<h4 class="font-mono font-bold text-lg mb-2">Structure</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Inputs are distilled into precise, structured requirements that are clear, consistent, and ready for execution.
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
					<h4 class="font-mono font-bold text-lg mb-2">Generate</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Scopes, proposals, plans, diagrams, configs, test scripts, and other artifacts are created in hours instead of weeks.
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
					<h4 class="font-mono font-bold text-lg mb-2">Handoff</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Artifacts stay traceable across sales, delivery, and client teams making handoffs seamless and efficient.
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
					<h4 class="font-mono font-bold text-lg mb-2">Align</h4>
					<p class="text-xs text-gray-600 leading-relaxed max-w-xs">
						Everything remains connected in one unified system, ensuring full visibility and keeping execution aligned across teams.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Customers Section -->
	<section class="bg-[#8c5a2e] text-white px-6 py-12 md:px-12 md:py-24">
		<div class="flex items-center gap-3 mb-12">
			<div class="w-1.5 h-1.5 bg-white rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Our Customers</span>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
			<div class="lg:col-span-6 lg:col-start-7 flex flex-col gap-8">
				<blockquote class="font-mono text-xl md:text-2xl leading-relaxed">
					"Auctor has quickly become an essential part of how we work at Valiantys. Our teams spend a significant amount of time gathering requirements, running discoveries, and shaping solution designs across multiple regions and practices. Auctor brings more speed, clarity, and consistency to that work, helping our people focus on value instead of friction. The improvement in collaboration and delivery quality has been immediate. As we continue to scale globally, Auctor is becoming a core enabler of how we operate."
				</blockquote>

				<div class="flex items-center gap-4 mt-4">
					<img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=200&auto=format&fit=crop" alt="Dan B." class="w-16 h-16 object-cover grayscale" />
					<div>
						<div class="font-mono font-bold text-sm">Dan B.</div>
						<div class="font-mono text-xs text-white/80">CIO of Valiantys, an Atlassian Platinum Solution Partner</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Security Section -->
	<section class="px-6 py-12 md:px-12 md:py-24">
		<div class="flex items-center gap-3 mb-8">
			<div class="w-1.5 h-1.5 bg-black rounded-full"></div>
			<span class="font-mono text-xs uppercase tracking-wider">Don't worry</span>
		</div>

		<h3 class="text-xl md:text-2xl font-mono max-w-3xl mb-16 leading-relaxed">
			Auctor is built with the same rigor that global system integrators and enterprise software vendors expect from mission-critical delivery platforms. Your data stays private, encrypted, and fully under your control.
		</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-12 gap-y-16">
			<!-- Item 1 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconGear}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Your Data,<br>Your Control</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					Auctor never uses your data to train AI models. Optional Zero Data Retention ensures your AI inputs are not logged or stored. You control access, retention, and deletion at every stage.
				</p>
			</div>

			<!-- Item 2 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconLock}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Secure, Encrypted<br>Infrastructure</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					Data is encrypted in transit and at rest (TLS 1.2 and above, AES-256) and processed on multi-region, highly available cloud infrastructure with continuous monitoring and redundancy.
				</p>
			</div>

			<!-- Item 3 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconFile}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Granular Retention &<br>Privacy Controls</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					Retention and deletion follow GDPR/CCPA-aligned workflows. You control how long data is stored and can delete it at any time.
				</p>
			</div>

			<!-- Item 4 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconAward}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Independently<br>Audited Compliance</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					SOC 2 Type II and ISO 27001 audited controls validate our commitments to security, availability, and confidentiality. Independent audits and regular penetration testing ensure ongoing compliance with global security standards.
				</p>
			</div>

			<!-- Item 5 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconKey}</div>
				<h4 class="font-mono font-bold text-sm mb-2">Enterprise Access &<br>Threat Protection</h4>
				<p class="text-xs text-gray-600 leading-relaxed">
					SSO and SCIM provisioning, MFA, and granular role-based access controls ensure alignment with your enterprise identity architecture. Continuous monitoring and automated alerting strengthen day-to-day platform security.
				</p>
			</div>

			<!-- Item 6 -->
			<div>
				<div class="mb-4 text-gray-500">{@html IconShield}</div>
				<h4 class="font-mono font-bold text-sm mb-2">We meet the highest level<br>of security certification</h4>
				<a href="#" class="inline-flex items-center gap-2 bg-black text-white text-xs font-mono py-2 px-4 mt-2 hover:bg-gray-800 transition">
					Our security portal {@html ArrowUpRight}
				</a>
			</div>
		</div>
	</section>

	<!-- CTA Section -->
	<section class="px-6 py-20 md:py-32 text-center">
		<h2 class="text-2xl md:text-4xl font-mono mb-8">You're going to want to see this</h2>
		<button class="bg-black text-white px-8 py-3 font-mono text-sm hover:bg-gray-800 transition">
			Book a demo
		</button>
	</section>

	<!-- Footer -->
	<footer class="bg-black text-white pt-16 pb-0 overflow-hidden">
		<div class="px-6 md:px-12 mb-16 flex flex-col md:flex-row justify-between gap-12">
			<div class="text-xs font-mono text-gray-400">
				© Auctor AI 2025
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
					<a href="mailto:info@getauctor.com" class="text-xs font-mono hover:text-gray-300">info@getauctor.com</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">Linkedin</a>
					<a href="#" class="text-xs font-mono hover:text-gray-300">x.com</a>
				</div>
			</div>
		</div>

		<!-- Big Logo -->
		<div class="w-full flex justify-center overflow-hidden">
			<div class="text-[15.5vw] leading-none font-black tracking-tighter text-white select-none relative" style="font-family: 'Inter', sans-serif;">
				AUCTOR
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

