<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cortame - Apoyemos el comercio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8FAFC;
        }
        /* Custom scrollbar for horizontal categories */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="text-slate-800 flex flex-col min-h-screen">

    <!-- Header / Navbar -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md shadow-sm border-b border-slate-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex items-center space-x-3 cursor-pointer" onclick="resetFilters()">
                    <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-emerald-500 to-teal-400 flex items-center justify-center text-white shadow-md shadow-emerald-200">
                        <i class="fa-solid font-bold fa-store text-lg"></i>
                    </div>
                    <div>
                        <span class="text-xl font-extrabold bg-gradient-to-r from-emerald-600 to-teal-700 bg-clip-text text-transparent">PuebloVivo</span>
                        <span class="text-xs block text-slate-500 font-medium -mt-1">Comercio Local</span>
                    </div>
                </div>

                <!-- Desktop Navigation -->
                <nav class="hidden md:flex space-x-8 font-medium text-slate-600">
                    <a href="#inicio" class="hover:text-emerald-600 transition-colors">Inicio</a>
                    <a href="#ofertas" class="hover:text-emerald-600 transition-colors">Ofertas del Día</a>
                    <a href="#directorio" class="hover:text-emerald-600 transition-colors">Directorio</a>
                    <a href="#registro" class="hover:text-emerald-600 transition-colors">Sumar mi Negocio</a>
                </nav>

                <!-- CTA Button -->
                <div class="flex items-center space-x-3">
                    <a href="#registro" class="hidden sm:inline-flex items-center px-4 py-2 border border-transparent text-sm font-semibold rounded-xl text-white bg-emerald-600 hover:bg-emerald-700 shadow-md shadow-emerald-200 transition-all duration-200 hover:-translate-y-0.5">
                        <i class="fa-solid fa-plus-circle mr-2"></i> Registrar Negocio
                    </a>
                </div>
            </div>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Section -->
        <section id="inicio" class="relative bg-gradient-to-b from-emerald-900 via-emerald-800 to-teal-900 text-white overflow-hidden py-16 lg:py-24">
            <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#fff_1px,transparent_1px)] [background-size:16px_16px]"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
                <span class="inline-block py-1 px-3 rounded-full bg-emerald-700/60 text-emerald-200 text-xs font-semibold tracking-wide uppercase mb-4 border border-emerald-500/30">
                    🌱 Apoya el talento y la economía de nuestra comunidad
                </span>
                <h1 class="text-3xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight mb-6 leading-tight">
                    Todo lo que necesitas en nuestro pueblo, <br class="hidden sm:inline">
                    <span class="text-emerald-300">a un solo clic de distancia.</span>
                </h1>
                <p class="text-lg sm:text-xl text-emerald-100/90 max-w-3xl mx-auto mb-10 font-light">
                    Encuentra restaurantes, productos artesanales, servicios y ofertas exclusivas de tus vecinos comerciantes. 
                </p>

                <!-- Main Search Bar -->
                <div class="max-w-2xl mx-auto">
                    <div class="bg-white p-2 rounded-2xl shadow-xl flex flex-col sm:flex-row items-center gap-2">
                        <div class="flex items-center w-full px-3 py-2 text-slate-700">
                            <i class="fa-solid fa-magnifying-glass text-slate-400 mr-3 text-lg"></i>
                            <input type="text" id="heroSearchInput" onkeyup="handleHeroSearch(event)" placeholder="¿Qué estás buscando? (ej. Panadería, Artesanías, Plomero)..." class="w-full text-sm sm:text-base focus:outline-none bg-transparent">
                        </div>
                        <button onclick="executeHeroSearch()" class="w-full sm:w-auto px-6 py-3.5 bg-emerald-600 hover:bg-emerald-700 text-white font-semibold rounded-xl shadow-md transition-all flex items-center justify-center shrink-0">
                            <span>Buscar</span>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Ofertas y Promociones del Día -->
        <section id="ofertas" class="py-12 bg-amber-50/50 border-b border-amber-100">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex flex-col md:flex-row md:items-end justify-between mb-8">
                    <div>
                        <div class="flex items-center space-x-2 text-amber-600 font-bold text-sm tracking-wide uppercase mb-1">
                            <i class="fa-solid fa-fire text-amber-500 animate-bounce"></i>
                            <span>Descuentos Especiales</span>
                        </div>
                        <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Ofertas de la Semana</h2>
                    </div>
                    <p class="text-slate-500 text-sm mt-2 md:mt-0">Aprovecha las promociones exclusivas del comercio local</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6" id="offersContainer">
                    <!-- Dynamic Offers render here -->
                </div>
            </div>
        </section>

        <!-- Directorio de Comercios -->
        <section id="directorio" class="py-16">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <!-- Header Section -->
                <div class="text-center max-w-3xl mx-auto mb-12">
                    <h2 class="text-3xl font-extrabold text-slate-900 sm:text-4xl mb-3">Directorio de Comercios</h2>
                    <p class="text-slate-600">Explora los negocios del pueblo, consulta sus horarios y ponte en contacto directo por WhatsApp.</p>
                </div>

                <!-- Category Filters (Horizontal Scrollable on Mobile) -->
                <div class="flex items-center gap-2 overflow-x-auto pb-4 mb-8 no-scrollbar justify-start md:justify-center" id="categoryContainer">
                    <!-- Dynamic Category buttons -->
                </div>

                <!-- Search & Results Count -->
                <div class="flex flex-col sm:flex-row justify-between items-center mb-8 gap-4 bg-white p-4 rounded-2xl border border-slate-100 shadow-sm">
                    <div class="relative w-full sm:w-96">
                        <i class="fa-solid fa-filter absolute left-3.5 top-1/2 -translate-y-1/2 text-slate-400"></i>
                        <input type="text" id="searchInput" oninput="filterBusinesses()" placeholder="Filtrar por nombre o producto..." class="w-full pl-10 pr-4 py-2 rounded-xl border border-slate-200 text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                    </div>
                    <div class="text-slate-500 text-sm font-medium">
                        Mostrando <span id="businessCount" class="font-bold text-emerald-600">0</span> comercios
                    </div>
                </div>

                <!-- Grid de Comercios -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8" id="businessGrid">
                    <!-- Dynamic Business Cards render here -->
                </div>

                <!-- Empty State -->
                <div id="emptyState" class="hidden text-center py-16 bg-white rounded-3xl border border-dashed border-slate-200 mt-6">
                    <div class="w-16 h-16 bg-slate-100 rounded-full flex items-center justify-center mx-auto mb-4 text-slate-400 text-2xl">
                        <i class="fa-solid fa-store-slash"></i>
                    </div>
                    <h3 class="text-lg font-bold text-slate-800">No se encontraron negocios</h3>
                    <p class="text-slate-500 text-sm mt-1">Prueba con otra palabra clave o cambia la categoría seleccionada.</p>
                    <button onclick="resetFilters()" class="mt-4 px-4 py-2 bg-emerald-100 text-emerald-700 rounded-xl font-medium text-sm hover:bg-emerald-200 transition">
                        Restablecer Filtros
                    </button>
                </div>
            </div>
        </section>

        <!-- Formulario de Registro para Comerciantes -->
        <section id="registro" class="py-16 bg-slate-900 text-white relative overflow-hidden">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center mb-12">
                    <span class="text-emerald-400 font-bold text-sm tracking-wider uppercase">¿Tienes un negocio en el pueblo?</span>
                    <h2 class="text-3xl font-extrabold sm:text-4xl mt-2">¡Inscribe tu Comercio Gratis!</h2>
                    <p class="text-slate-400 mt-3 text-sm sm:text-base max-w-xl mx-auto">
                        Aumenta tus ventas y llega a más vecinos digitalizando tu negocio. Completa el formulario y aparecerás de inmediato en el directorio.
                    </p>
                </div>

                <div class="bg-slate-800 border border-slate-700/60 p-6 sm:p-10 rounded-3xl shadow-2xl">
                    <form id="merchantForm" onsubmit="handleRegister(event)" class="space-y-6">
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                            <!-- Nombre del negocio -->
                            <div>
                                <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Nombre del Comercio *</label>
                                <input type="text" id="regName" required placeholder="Ej. Tienda Doña María" class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition">
                            </div>

                            <!-- Categoría -->
                            <div>
                                <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Categoría *</label>
                                <select id="regCategory" required class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition">
                                    <option value="" disabled selected>Selecciona una categoría</option>
                                    <option value="Alimentos y Abarrotes">Alimentos y Abarrotes</option>
                                    <option value="Gastronomía y Restaurantes">Gastronomía y Restaurantes</option>
                                    <option value="Salud y Farmacia">Salud y Farmacia</option>
                                    <option value="Ropa y Calzado">Ropa y Calzado</option>
                                    <option value="Ferretería y Agrícola">Ferretería y Agrícola</option>
                                    <option value="Artesanías y Recuerdos">Artesanías y Recuerdos</option>
                                    <option value="Servicios Profesionales">Servicios Profesionales</option>
                                    <option value="Belleza y Peluquería">Belleza y Peluquería</option>
                                    <option value="Turismo y Alojamiento">Turismo y Alojamiento</option>
                                    <option value="Transporte y Envíos">Transporte y Envíos</option>
                                    <option value="Reparaciones y Oficios">Reparaciones y Oficios</option>
                                </select>
                            </div>

                            <!-- Teléfono / WhatsApp -->
                            <div>
                                <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Teléfono / WhatsApp *</label>
                                <input type="tel" id="regPhone" required placeholder="Ej. +573101234567" class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition">
                            </div>

                            <!-- Horario -->
                            <div>
                                <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Horario de Atención *</label>
                                <input type="text" id="regHours" required placeholder="Ej. Lun-Sáb: 8:00 AM - 6:00 PM" class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition">
                            </div>
                        </div>

                        <!-- Dirección -->
                        <div>
                            <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Dirección o Ubicación *</label>
                            <input type="text" id="regAddress" required placeholder="Ej. Calle Principal #12-45 (Frente al Parque)" class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition">
                        </div>

                        <!-- Descripción -->
                        <div>
                            <label class="block text-xs font-semibold uppercase text-slate-300 mb-2">Descripción de productos o servicios *</label>
                            <textarea id="regDescription" rows="3" required placeholder="Cuenta qué vende tu negocio, especialidades, envíos a domicilio, etc..." class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-4 py-3 text-white placeholder-slate-500 text-sm focus:outline-none focus:border-emerald-500 focus:ring-1 focus:ring-emerald-500 transition"></textarea>
                        </div>

                        <!-- Submit Button -->
                        <button type="submit" class="w-full bg-emerald-500 hover:bg-emerald-600 text-slate-950 font-bold py-4 rounded-xl shadow-lg transition-all duration-200 transform hover:-translate-y-0.5 flex items-center justify-center space-x-2">
                            <i class="fa-solid fa-paper-plane"></i>
                            <span>Publicar mi Comercio Ahora</span>
                        </button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- Modal de Confirmación -->
    <div id="toastModal" class="fixed bottom-5 right-5 z-50 transform translate-y-24 opacity-0 transition-all duration-300">
        <div class="bg-emerald-600 text-white px-6 py-4 rounded-2xl shadow-xl flex items-center space-x-3">
            <i class="fa-solid fa-circle-check text-2xl"></i>
            <div>
                <h4 class="font-bold">¡Registro Exitoso!</h4>
                <p class="text-xs text-emerald-100">Tu comercio se ha agregado al directorio.</p>
            </div>
        </div>
    </div>

    <!-- Modal de Mapa / Ubicación Simulada -->
    <div id="mapModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-lg rounded-3xl p-6 shadow-2xl relative">
            <button onclick="closeMapModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600 w-8 h-8 rounded-full bg-slate-100 flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div class="flex items-center space-x-3 mb-4">
                <div class="w-10 h-10 rounded-xl bg-emerald-100 text-emerald-600 flex items-center justify-center">
                    <i class="fa-solid fa-location-dot text-lg"></i>
                </div>
                <div>
                    <h3 id="modalBusinessName" class="font-bold text-slate-900 text-lg">Ubicación del Comercio</h3>
                    <p id="modalBusinessAddress" class="text-xs text-slate-500">Dirección</p>
                </div>
            </div>
            
            <!-- Map Simulation Box -->
            <div class="bg-slate-100 rounded-2xl h-64 relative overflow-hidden flex items-center justify-center border border-slate-200">
                <div class="absolute inset-0 bg-[radial-gradient(#cbd5e1_1px,transparent_1px)] [background-size:12px_12px] opacity-60"></div>
                <!-- Simulated map pins & road -->
                <div class="w-full h-12 bg-slate-200/80 transform -rotate-12 absolute"></div>
                <div class="w-12 h-full bg-slate-200/80 transform -rotate-12 absolute"></div>
                
                <div class="relative z-10 text-center animate-bounce">
                    <i class="fa-solid fa-location-dot text-4xl text-rose-500 drop-shadow-md"></i>
                    <div class="bg-slate-900 text-white text-[10px] font-bold px-2 py-1 rounded-md mt-1 shadow-md">
                        ¡Aquí está!
                    </div>
                </div>
            </div>

            <p class="text-xs text-slate-400 text-center mt-3">Simulación de mapa interactivo para comercios del pueblo.</p>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-slate-950 text-slate-400 py-10 border-t border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center sm:text-left flex flex-col sm:flex-row justify-between items-center gap-4">
            <div>
                <p class="font-semibold text-slate-200">PuebloVivo - Impulsando Nuestra Economía Local</p>
                <p class="text-xs text-slate-500 mt-1">Plataforma comunitaria diseñada para conectar vecinos y comerciantes.</p>
            </div>
            <div class="flex space-x-6 text-sm">
                <a href="#directorio" class="hover:text-emerald-400 transition">Directorio</a>
                <a href="#ofertas" class="hover:text-emerald-400 transition">Ofertas</a>
                <a href="#registro" class="hover:text-emerald-400 transition">Registrarse</a>
            </div>
        </div>
    </footer>

    <!-- JavaScript Application Logic -->
    <script>
        // Initial Mock Business Data - Vacío para que los vecinos comiencen a inscribirse
        let businesses = [];

        // Offers Data
        const offers = [
            {
                title: "Inscripción Gratuita para Comercios",
                business: "Alcaldía & Junta Local",
                discount: "GRATIS",
                validity: "Registra tu negocio hoy mismo",
                badgeBg: "bg-emerald-600",
                icon: "fa-store"
            },
            {
                title: "Visibilidad Digital para Tu Negocio",
                business: "Comercio del Pueblo",
                discount: "NUEVO",
                validity: "Conecta directamente por WhatsApp",
                badgeBg: "bg-teal-600",
                icon: "fa-bullhorn"
            }
        ];

        // Amplia lista de categorías locales y rurales
        const categories = [
            "Todos",
            "Alimentos y Abarrotes",
            "Gastronomía y Restaurantes",
            "Salud y Farmacia",
            "Ropa y Calzado",
            "Ferretería y Agrícola",
            "Artesanías y Recuerdos",
            "Servicios Profesionales",
            "Belleza y Peluquería",
            "Turismo y Alojamiento",
            "Transporte y Envíos",
            "Reparaciones y Oficios"
        ];

        let selectedCategory = "Todos";

        // Initialize App
        document.addEventListener("DOMContentLoaded", () => {
            renderCategories();
            renderOffers();
            renderBusinesses();
        });

        // Render Categories
        function renderCategories() {
            const container = document.getElementById("categoryContainer");
            container.innerHTML = categories.map(cat => {
                const isActive = cat === selectedCategory;
                return `
                    <button 
                        onclick="setCategory('${cat}')"
                        class="px-5 py-2.5 rounded-xl font-medium text-sm whitespace-nowrap transition-all duration-200 border ${
                            isActive 
                            ? 'bg-emerald-600 text-white border-emerald-600 shadow-md shadow-emerald-200' 
                            : 'bg-white text-slate-600 border-slate-200 hover:bg-slate-50'
                        }">
                        ${cat}
                    </button>
                `;
            }).join('');
        }

        // Render Offers
        function renderOffers() {
            const container = document.getElementById("offersContainer");
            container.innerHTML = offers.map(offer => `
                <div class="bg-white rounded-2xl p-6 border border-amber-200/70 shadow-sm relative overflow-hidden flex flex-col justify-between hover:shadow-md transition">
                    <div class="absolute -right-4 -top-4 w-20 h-20 bg-amber-100 rounded-full opacity-40"></div>
                    <div>
                        <div class="flex justify-between items-start mb-3">
                            <span class="${offer.badgeBg} text-white font-black text-xs px-3 py-1 rounded-full uppercase tracking-wider">
                                ${offer.discount}
                            </span>
                            <i class="fa-solid ${offer.icon} text-amber-500 text-xl"></i>
                        </div>
                        <h3 class="font-bold text-slate-900 text-lg mb-1">${offer.title}</h3>
                        <p class="text-xs font-semibold text-emerald-700 mb-3"><i class="fa-solid fa-store mr-1"></i> ${offer.business}</p>
                    </div>
                    <div class="pt-3 border-t border-slate-100 flex items-center justify-between text-xs text-slate-400">
                        <span><i class="fa-regular fa-clock mr-1"></i> ${offer.validity}</span>
                    </div>
                </div>
            `).join('');
        }

        // Set Filter Category
        function setCategory(cat) {
            selectedCategory = cat;
            renderCategories();
            filterBusinesses();
        }

        // Main Filter & Render Logic
        function filterBusinesses() {
            const query = document.getElementById("searchInput").value.toLowerCase();
            
            const filtered = businesses.filter(b => {
                const matchesCategory = selectedCategory === "Todos" || b.category === selectedCategory;
                const matchesSearch = b.name.toLowerCase().includes(query) || 
                                      b.description.toLowerCase().includes(query) ||
                                      b.category.toLowerCase().includes(query);
                return matchesCategory && matchesSearch;
            });

            renderBusinesses(filtered);
        }

        // Render Business Cards Grid
        function renderBusinesses(data = businesses) {
            const grid = document.getElementById("businessGrid");
            const emptyState = document.getElementById("emptyState");
            const countLabel = document.getElementById("businessCount");

            countLabel.textContent = data.length;

            if (data.length === 0) {
                grid.innerHTML = "";
                emptyState.classList.remove("hidden");
                return;
            }

            emptyState.classList.add("hidden");

            grid.innerHTML = data.map(item => `
                <div class="bg-white rounded-3xl border border-slate-100 shadow-sm overflow-hidden flex flex-col hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1">
                    <!-- Image with Tag -->
                    <div class="relative h-48 w-full bg-slate-100 overflow-hidden">
                        <img src="${item.image}" alt="${item.name}" loading="lazy" class="w-full h-full object-cover" onerror="this.src='https://placehold.co/600x400/10b981/ffffff?text=${encodeURIComponent(item.name)}'">
                        <span class="absolute top-3 left-3 bg-white/90 backdrop-blur-md text-slate-800 text-xs font-semibold px-3 py-1 rounded-full shadow-sm">
                            ${item.category}
                        </span>
                    </div>

                    <!-- Content -->
                    <div class="p-6 flex-grow flex flex-col justify-between">
                        <div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2">${item.name}</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-4 line-clamp-3">${item.description}</p>
                            
                            <!-- Info Badges -->
                            <div class="space-y-2 text-xs text-slate-500 mb-6">
                                <div class="flex items-center">
                                    <i class="fa-solid fa-clock text-emerald-600 w-5"></i>
                                    <span>${item.hours}</span>
                                </div>
                                <div class="flex items-center">
                                    <i class="fa-solid fa-location-dot text-emerald-600 w-5"></i>
                                    <span class="truncate">${item.address}</span>
                                </div>
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="grid grid-cols-2 gap-3 pt-4 border-t border-slate-100">
                            <!-- WhatsApp Link -->
                            <a href="https://wa.me/${item.phone.replace(/[^0-9]/g, '')}?text=${encodeURIComponent('¡Hola! Los vi en PuebloVivo y quisiera hacer una consulta.')}" target="_blank" class="flex items-center justify-center space-x-2 bg-emerald-50 hover:bg-emerald-100 text-emerald-700 py-2.5 px-3 rounded-xl font-semibold text-xs transition">
                                <i class="fa-brands fa-whatsapp text-emerald-600 text-base"></i>
                                <span>WhatsApp</span>
                            </a>
                            <!-- Location Modal Button -->
                            <button onclick="openMapModal('${item.name.replace(/'/g, "\\'")}', '${item.address.replace(/'/g, "\\'")}')" class="flex items-center justify-center space-x-2 bg-slate-50 hover:bg-slate-100 text-slate-700 py-2.5 px-3 rounded-xl font-semibold text-xs transition">
                                <i class="fa-solid fa-map-location-dot text-slate-500"></i>
                                <span>Ubicación</span>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Hero Search Handlers
        function handleHeroSearch(event) {
            if (event.key === 'Enter') {
                executeHeroSearch();
            }
        }

        function executeHeroSearch() {
            const query = document.getElementById("heroSearchInput").value;
            document.getElementById("searchInput").value = query;
            selectedCategory = "Todos";
            renderCategories();
            filterBusinesses();
            
            // Smooth scroll to directory
            document.getElementById("directorio").scrollIntoView({ behavior: 'smooth' });
        }

        // Reset All Filters
        function resetFilters() {
            selectedCategory = "Todos";
            document.getElementById("searchInput").value = "";
            document.getElementById("heroSearchInput").value = "";
            renderCategories();
            filterBusinesses();
        }

        // Register New Business
        function handleRegister(event) {
            event.preventDefault();

            const name = document.getElementById("regName").value;
            const category = document.getElementById("regCategory").value;
            const phone = document.getElementById("regPhone").value;
            const hours = document.getElementById("regHours").value;
            const address = document.getElementById("regAddress").value;
            const description = document.getElementById("regDescription").value;

            // Image assignment based on category
            let defaultImg = "https://images.unsplash.com/photo-1528698827591-e19ccd7bc23d?auto=format&fit=crop&w=600&q=80";
            if (category.includes("Gastronomía")) defaultImg = "https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=600&q=80";
            if (category.includes("Artesanías")) defaultImg = "https://images.unsplash.com/photo-1513519245088-0e12902e5a38?auto=format&fit=crop&w=600&q=80";
            if (category.includes("Ferretería")) defaultImg = "https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&w=600&q=80";
            if (category.includes("Salud")) defaultImg = "https://images.unsplash.com/photo-1584308666744-24d5c474f2ae?auto=format&fit=crop&w=600&q=80";
            if (category.includes("Alimentos")) defaultImg = "https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=600&q=80";

            const newBusiness = {
                id: Date.now(),
                name,
                category,
                phone,
                hours,
                address,
                description,
                image: defaultImg
            };

            // Add to top of list
            businesses.unshift(newBusiness);

            // Reset Form & Update View
            document.getElementById("merchantForm").reset();
            resetFilters();

            // Show Toast Notification
            showToast();

            // Scroll to newly added item in directory
            document.getElementById("directorio").scrollIntoView({ behavior: 'smooth' });
        }

        // Toast Notification Trigger
        function showToast() {
            const toast = document.getElementById("toastModal");
            toast.classList.remove("translate-y-24", "opacity-0");
            toast.classList.add("translate-y-0", "opacity-100");

            setTimeout(() => {
                toast.classList.remove("translate-y-0", "opacity-100");
                toast.classList.add("translate-y-24", "opacity-0");
            }, 4000);
        }

        // Map Modal Control
        function openMapModal(name, address) {
            document.getElementById("modalBusinessName").textContent = name;
            document.getElementById("modalBusinessAddress").textContent = address;
            document.getElementById("mapModal").classList.remove("hidden");
        }

        function closeMapModal() {
            document.getElementById("mapModal").classList.add("hidden");
        }
    </script>
</body>
</html>
