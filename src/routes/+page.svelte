<!-- src/routes/+page.svelte -->
<script>
    // Optionally, add interactivity here
</script>

<div class="min-h-screen bg-gray-100 font-sans">
    <!-- Header -->
    <header class="flex items-center justify-between p-6 bg-white shadow-md">
        <div class="text-2xl font-bold text-blue-600">ShipIt Interactive</div>
        <nav class="space-x-6 text-gray-700">
            <a href="#services" class="hover:text-blue-600">Services</a>
            <a href="#projects" class="hover:text-blue-600">Projects</a>
            <a href="#about" class="hover:text-blue-600">About</a>
            <a href="#contact" class="hover:text-blue-600">Contact</a>
        </nav>
        <a href="#contact" class="px-4 py-2 text-white bg-blue-600 rounded hover:bg-blue-700">Get in Touch</a>
    </header>

    <!-- Hero Section -->
    <section class="flex flex-col items-center justify-center h-screen text-center bg-gradient-to-r from-blue-500 to-blue-600 text-white">
        <h1 class="text-4xl font-bold md:text-6xl">Delivering Software Solutions That Ship</h1>
        <p class="mt-4 text-lg md:text-2xl">Your partner in creating efficient, scalable software for modern challenges.</p>
        <a href="#services" class="px-8 py-3 mt-8 text-lg bg-white text-blue-600 rounded-full hover:bg-gray-100">Get Started</a>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-16 bg-white">
        <h2 class="text-3xl font-bold text-center text-gray-800">Our Expertise</h2>
        <div class="grid grid-cols-1 gap-8 mt-8 md:grid-cols-2 lg:grid-cols-4">
            <div class="p-6 text-center bg-gray-50 rounded shadow">
                <div class="text-xl font-semibold text-blue-600">Custom Software Development</div>
                <p class="mt-2 text-gray-600">Tailored solutions to meet unique business needs.</p>
            </div>
            <div class="p-6 text-center bg-gray-50 rounded shadow">
                <div class="text-xl font-semibold text-blue-600">Cloud Solutions</div>
                <p class="mt-2 text-gray-600">Scalable and secure cloud services for modern infrastructure.</p>
            </div>
            <div class="p-6 text-center bg-gray-50 rounded shadow">
                <div class="text-xl font-semibold text-blue-600">Mobile and Web Apps</div>
                <p class="mt-2 text-gray-600">Engaging, user-friendly mobile and web applications.</p>
            </div>
            <div class="p-6 text-center bg-gray-50 rounded shadow">
                <div class="text-xl font-semibold text-blue-600">Consulting & Strategy</div>
                <p class="mt-2 text-gray-600">Expert guidance to navigate complex tech landscapes.</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-16 bg-gray-100">
        <h2 class="text-3xl font-bold text-center text-gray-800">Projects that Make an Impact</h2>
        <div class="grid grid-cols-1 gap-8 mt-8 md:grid-cols-2 lg:grid-cols-3">
            <!-- Repeat project items as needed -->
            <div class="p-6 bg-white rounded shadow">
                <div class="text-xl font-semibold text-blue-600">Project Name</div>
                <p class="mt-2 text-gray-600">Brief project description highlighting impact and value.</p>
            </div>
            <!-- Add more projects here -->
        </div>
    </section>

    <!-- About Us Section -->
    <section id="about" class="py-16 bg-white">
        <h2 class="text-3xl font-bold text-center text-gray-800">About ShipIt Interactive</h2>
        <p class="max-w-3xl px-4 mx-auto mt-4 text-center text-gray-600">ShipIt Interactive is a software firm dedicated to delivering high-quality, scalable solutions to meet the needs of modern businesses. Our team combines technical expertise with a client-first approach.</p>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-16 bg-gray-100">
        <h2 class="text-3xl font-bold text-center text-gray-800">Let’s Work Together</h2>
        <div class="max-w-lg px-4 py-8 mx-auto bg-white rounded shadow-md">
            <form>
                <label class="block text-sm font-medium text-gray-700">Name</label>
                <input type="text" class="w-full px-3 py-2 mt-1 border rounded" />
                
                <label class="block mt-4 text-sm font-medium text-gray-700">Email</label>
                <input type="email" class="w-full px-3 py-2 mt-1 border rounded" />
                
                <label class="block mt-4 text-sm font-medium text-gray-700">Message</label>
                <textarea class="w-full px-3 py-2 mt-1 border rounded"></textarea>
                
                <button type="submit" class="w-full px-4 py-2 mt-6 text-white bg-blue-600 rounded hover:bg-blue-700">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-6 text-center bg-white">
        <p class="text-sm text-gray-600">© 2024 ShipIt Interactive. All rights reserved.</p>
    </footer>
</div>
