<!-- src/routes/+page.svelte -->
<script>
    // Smooth scrolling for anchor links
    function scrollToSection(id) {
        document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
    }

    // Handle form submission to open Gmail
    function handleSubmit(event) {
        event.preventDefault();
        
        const formData = new FormData(event.target);
        const name = formData.get('name') || '';
        const email = formData.get('email') || '';
        const message = formData.get('message') || '';
        
        // Create Gmail compose URL with pre-filled data
        const subject = encodeURIComponent(`Contact from ${name} - ShipIt Interactive`);
        const body = encodeURIComponent(`Name: ${name}\nEmail: ${email}\n\nMessage:\n${message}`);
        const gmailUrl = `https://mail.google.com/mail/?view=cm&fs=1&to=email@mufassir.net&su=${subject}&body=${body}`;
        
        // Open Gmail in a new tab
        window.open(gmailUrl, '_blank');
    }
</script>

<div class="min-h-screen bg-white font-sans">
    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-white/95 backdrop-blur-sm border-b border-gray-100">
        <div class="max-w-7xl mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <div class="text-2xl font-bold bg-gradient-to-r from-indigo-600 to-purple-600 bg-clip-text text-transparent">
                    ShipIt Interactive
                </div>
                <nav class="hidden md:flex space-x-8">
                    <button on:click={() => scrollToSection('services')} class="text-gray-600 hover:text-indigo-600 transition-colors duration-200">Services</button>
                    <button on:click={() => scrollToSection('about')} class="text-gray-600 hover:text-indigo-600 transition-colors duration-200">About</button>
                    <button on:click={() => scrollToSection('contact')} class="text-gray-600 hover:text-indigo-600 transition-colors duration-200">Contact</button>
                </nav>
                <button on:click={() => scrollToSection('contact')} class="px-6 py-2 bg-gradient-to-r from-indigo-600 to-purple-600 text-white rounded-full hover:from-indigo-700 hover:to-purple-700 transition-all duration-200 shadow-lg hover:shadow-xl">
                    Get Started
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-indigo-50 via-white to-purple-50 overflow-hidden">
        <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
        <div class="relative max-w-6xl mx-auto px-6 text-center">
            <div class="mb-8">
                <div class="inline-flex items-center px-4 py-2 bg-indigo-100 text-indigo-700 rounded-full text-sm font-medium mb-6">
                    <span class="w-2 h-2 bg-indigo-500 rounded-full mr-2"></span>
                    Innovative Software Solutions
                </div>
            </div>
            <h1 class="text-5xl md:text-7xl font-bold text-gray-900 mb-6 leading-tight">
                We Build
                <span class="bg-gradient-to-r from-indigo-600 to-purple-600 bg-clip-text text-transparent">Software</span>
                <br>That Ships
            </h1>
            <p class="text-xl md:text-2xl text-gray-600 mb-12 max-w-3xl mx-auto leading-relaxed">
                Your partner in creating efficient, scalable software solutions for modern business challenges.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center">
                <button on:click={() => scrollToSection('services')} class="px-8 py-4 bg-gradient-to-r from-indigo-600 to-purple-600 text-white rounded-full text-lg font-semibold hover:from-indigo-700 hover:to-purple-700 transition-all duration-200 shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                    Explore Our Services
                </button>
                <button on:click={() => scrollToSection('about')} class="px-8 py-4 border-2 border-gray-300 text-gray-700 rounded-full text-lg font-semibold hover:border-indigo-600 hover:text-indigo-600 transition-all duration-200">
                    Learn More
                </button>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Our Expertise</h2>
                <p class="text-xl text-gray-600 max-w-3xl mx-auto">
                    We specialize in delivering cutting-edge software solutions that drive business growth and innovation.
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="group p-8 bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl hover:from-indigo-100 hover:to-purple-100 transition-all duration-300 transform hover:-translate-y-2">
                    <div class="w-12 h-12 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"></path>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-4">Custom Development</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Tailored software solutions designed to meet your unique business requirements and challenges.
                    </p>
                </div>

                <div class="group p-8 bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl hover:from-indigo-100 hover:to-purple-100 transition-all duration-300 transform hover:-translate-y-2">
                    <div class="w-12 h-12 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z"></path>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-4">Cloud Solutions</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Scalable and secure cloud infrastructure designed for modern business needs.
                    </p>
                </div>

                <div class="group p-8 bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl hover:from-indigo-100 hover:to-purple-100 transition-all duration-300 transform hover:-translate-y-2">
                    <div class="w-12 h-12 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z"></path>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-4">Mobile & Web Apps</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Engaging, user-friendly applications that deliver exceptional user experiences.
                    </p>
                </div>

                <div class="group p-8 bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl hover:from-indigo-100 hover:to-purple-100 transition-all duration-300 transform hover:-translate-y-2">
                    <div class="w-12 h-12 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-4">Consulting</h3>
                    <p class="text-gray-600 leading-relaxed">
                        Expert guidance to help you navigate complex technology landscapes and make informed decisions.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 bg-gradient-to-br from-gray-50 to-indigo-50">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
                <div>
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">About ShipIt Interactive</h2>
                    <p class="text-xl text-gray-600 mb-8 leading-relaxed">
                        We are a passionate team of software engineers, designers, and strategists dedicated to delivering high-quality, scalable solutions that drive real business value.
                    </p>
                    <p class="text-xl text-gray-600 mb-8 leading-relaxed">
                        Our approach combines technical expertise with a deep understanding of business needs, ensuring every solution we deliver not only meets requirements but exceeds expectations.
                    </p>
                    <div class="flex flex-wrap gap-4">
                        <div class="flex items-center text-gray-600">
                            <div class="w-2 h-2 bg-indigo-600 rounded-full mr-3"></div>
                            <span>3+ Years Experience</span>
                        </div>
                        <div class="flex items-center text-gray-600">
                            <div class="w-2 h-2 bg-indigo-600 rounded-full mr-3"></div>
                            <span>50+ Projects Delivered</span>
                        </div>
                        <div class="flex items-center text-gray-600">
                            <div class="w-2 h-2 bg-indigo-600 rounded-full mr-3"></div>
                            <span>100% Client Satisfaction</span>
                        </div>
                    </div>
                </div>
                <div class="relative">
                    <div class="bg-gradient-to-br from-indigo-600 to-purple-600 rounded-3xl p-8 text-white">
                        <h3 class="text-2xl font-bold mb-6">Why Choose Us?</h3>
                        <div class="space-y-4">
                            <div class="flex items-start">
                                <div class="w-6 h-6 bg-white/20 rounded-full flex items-center justify-center mr-4 mt-1">
                                    <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                    </svg>
                                </div>
                                <div>
                                    <h4 class="font-semibold mb-1">Proven Track Record</h4>
                                    <p class="text-white/80 text-sm">Successfully delivered projects across various industries</p>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="w-6 h-6 bg-white/20 rounded-full flex items-center justify-center mr-4 mt-1">
                                    <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                    </svg>
                                </div>
                                <div>
                                    <h4 class="font-semibold mb-1">Modern Technologies</h4>
                                    <p class="text-white/80 text-sm">Using the latest tools and frameworks for optimal performance</p>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="w-6 h-6 bg-white/20 rounded-full flex items-center justify-center mr-4 mt-1">
                                    <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                    </svg>
                                </div>
                                <div>
                                    <h4 class="font-semibold mb-1">Dedicated Support</h4>
                                    <p class="text-white/80 text-sm">Ongoing support and maintenance for all our solutions</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 bg-white">
        <div class="max-w-4xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6">Let's Work Together</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">
                    Ready to bring your ideas to life? Get in touch and let's discuss how we can help you achieve your goals.
                </p>
            </div>
            
            <div class="bg-gradient-to-br from-indigo-50 to-purple-50 rounded-3xl p-8 md:p-12">
                <form class="space-y-6" on:submit={handleSubmit}>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Name</label>
                            <input name="name" type="text" class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all duration-200" placeholder="Your name" required />
                        </div>
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Email</label>
                            <input name="email" type="email" class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all duration-200" placeholder="your@email.com" required />
                        </div>
                    </div>
                    
                    <div>
                        <label class="block text-sm font-semibold text-gray-700 mb-2">Message</label>
                        <textarea name="message" rows="6" class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all duration-200" placeholder="Tell us about your project..." required></textarea>
                    </div>
                    
                    <button type="submit" class="w-full px-8 py-4 bg-gradient-to-r from-indigo-600 to-purple-600 text-white rounded-xl text-lg font-semibold hover:from-indigo-700 hover:to-purple-700 transition-all duration-200 shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                        Send Message
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 bg-gray-900 text-white">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center">
                <div class="text-2xl font-bold bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent mb-4">
                    ShipIt Interactive
                </div>
                <p class="text-gray-400 mb-8">
                    Delivering innovative software solutions that drive business growth and success.
                </p>
                <div class="border-t border-gray-800 pt-8">
                    <p class="text-sm text-gray-500">
                        © 2025 ShipIt Interactive. All rights reserved.
                    </p>
                </div>
            </div>
        </div>
    </footer>
</div>

<style>
    .bg-grid-pattern {
        background-image: 
            linear-gradient(rgba(99, 102, 241, 0.1) 1px, transparent 1px),
            linear-gradient(90deg, rgba(99, 102, 241, 0.1) 1px, transparent 1px);
        background-size: 50px 50px;
    }
</style>
