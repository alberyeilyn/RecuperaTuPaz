[index.html](https://github.com/user-attachments/files/24076318/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recupera el Control en 21 Días - Método Natural</title>
    
    <!-- Script para cargar Tailwind CSS y Chart.js -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <style>
        /* Custom Font Import - Inter is modern and clean */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap');
        
        /* Aplicar estilos globales al contenedor principal que envuelve todo */
        .app-wrapper {
            font-family: 'Inter', sans-serif;
            background-color: #fafaf9; /* stone-50 */
            color: #44403c; /* stone-700 */
            padding-bottom: 80px; /* Espacio para el botón flotante */
        }

        /* Chart Container Styling */
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }

        /* Navigation Active State */
        .nav-btn-local.active {
            background-color: #e11d48; /* rose-600 */
            color: white;
            font-weight: 600;
        }

        /* Smooth transitions */
        .transition-all-300 {
            transition: all 0.3s ease-in-out;
        }
        
        /* Custom scrollbar for module list */
        .custom-scroll::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: #d6d3d1;
            border-radius: 10px;
        }

        /* Animation for Fluorescent Button */
        @keyframes pulse-neon {
            0% { box-shadow: 0 0 5px #a3e635, 0 0 10px #a3e635, 0 0 15px #a3e635, 0 0 20px #a3e635; }
            50% { box-shadow: 0 0 10px #a3e635, 0 0 20px #a3e635, 0 0 30px #a3e635, 0 0 40px #a3e635; }
            100% { box-shadow: 0 0 5px #a3e635, 0 0 10px #a3e635, 0 0 15px #a3e635, 0 0 20px #a3e635; }
        }

        .fluorescent-btn {
            background-color: #a3e635; /* lime-400 */
            color: #1a2e05; /* dark green text for contrast */
            position: fixed; 
            bottom: 20px;
            right: 20px;
            z-index: 1000;
            padding: 1rem 1.5rem;
            border-radius: 9999px; /* full rounded */
            font-weight: 700;
            text-align: center;
            animation: pulse-neon 1.5s infinite alternate;
            transition: all 0.2s ease-in-out;
            cursor: pointer;
            text-shadow: 1px 1px 0 #d9f99d; /* subtle text shadow for lift */
        }
        .fluorescent-btn:hover {
            transform: scale(1.05);
            background-color: #bef264; /* lime-300 on hover */
        }

        /* --- Estilos para el Carrusel de Testimonios --- */
        .carousel-container {
            min-height: 450px; /* Asegura un buen espacio para la card */
            position: relative;
        }
        .testimonial-card {
            transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
        }
        .testimonial-card.hidden {
            opacity: 0;
            position: absolute; 
            pointer-events: none;
            z-index: 0;
        }
        .testimonial-card.active {
            opacity: 1;
            position: relative;
            z-index: 10;
        }
        
        /* Estilo para la imagen del testimonio */
        .testimonial-image {
            max-width: 100%;
            height: auto;
            display: block;
            border-radius: 0.75rem; /* rounded-xl */
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); /* shadow-xl */
            margin: 0 auto;
        }
        /* Limitar el ancho de la imagen en escritorio para que no se estire demasiado */
        @media (min-width: 768px) {
            .testimonial-image {
                max-width: 70%;
            }
        }
    </style>
</head>
<body>

    <!-- CONTENIDO PRINCIPAL: Envuelto en un contenedor para simular el body -->
    <div class="app-wrapper">
        <div class="container mx-auto px-4 py-8 max-w-5xl">

            <!-- Navegación Local (Simplificada) -->
            <div class="mb-8 p-3 bg-white rounded-lg shadow-md flex flex-wrap justify-center gap-2 sticky top-0 z-50">
                <button onclick="navigate('home')" class="nav-btn-local active px-3 py-2 rounded-lg text-sm transition-colors bg-rose-600 text-white" id="btn-home">Inicio</button>
                <button onclick="navigate('method')" class="nav-btn-local px-3 py-2 rounded-lg text-sm transition-colors hover:bg-rose-50" id="btn-method">Método</button>
                <button onclick="navigate('modules')" class="nav-btn-local px-3 py-2 rounded-lg text-sm transition-colors hover:bg-rose-50" id="btn-modules">Módulos</button>
                <button onclick="navigate('testimonials')" class="nav-btn-local px-3 py-2 rounded-lg text-sm transition-colors hover:bg-rose-50" id="btn-testimonials">Testimonios</button>
                <button onclick="navigate('offer')" class="nav-btn-local px-3 py-2 rounded-lg text-sm transition-colors hover:bg-rose-50" id="btn-offer">Oferta</button>
            </div>
            
            <!-- SECTION: HOME / DIAGNOSIS -->
            <section id="home" class="view-section animate-fade-in block">
                <!-- Hero -->
                <div class="text-center mb-12">
                    <span class="bg-rose-100 text-rose-700 text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wide">Método Natural</span>
                    <h1 class="text-3xl md:text-5xl font-bold text-stone-800 mt-4 mb-4 leading-tight">
                        Recupera el Control de Tu Cuerpo en <span class="text-rose-600">21 Días</span>
                    </h1>
                    <p class="text-lg text-stone-600 max-w-2xl mx-auto mb-8">
                        Reduce brotes, fortalece tu inmunidad y recupera tu paz. Un método práctico hecho para mujeres que necesitan resultados reales.
                    </p>
                    <div class="flex flex-col sm:flex-row justify-center gap-4">
                        <!-- ENLACE DE PAGO PRINCIPAL -->
                        <a href="https://shop.beacons.ai/eilynalbarran/ff3e881c-9199-4c6f-a89e-b0a707ce3200" target="_blank" class="bg-rose-600 text-white font-bold py-3 px-8 rounded-full shadow-lg hover:bg-rose-700 transition-transform transform hover:-translate-y-1 inline-block">
                            Quiero mi plan ahora ➔
                        </a>
                    </div>
                </div>

                <!-- Context Block -->
                <div class="bg-white rounded-2xl p-6 md:p-8 shadow-sm border border-stone-100 mb-12">
                    <h3 class="text-xl font-bold text-stone-800 mb-4 border-l-4 border-rose-500 pl-3">Tu Situación Actual</h3>
                    <p class="text-stone-600 mb-6">
                        Esta sección te ayuda a identificar si este plan resuena con tu experiencia actual. Selecciona las frases que describen cómo te sientes hoy para ver si este método se alinea con tus necesidades.
                    </p>

                    <div class="grid md:grid-cols-2 gap-8 items-center">
                        <div>
                            <div id="pain-points-list" class="space-y-3">
                                <!-- JS Generated Checkboxes -->
                            </div>
                        </div>
                        <div class="bg-stone-50 p-6 rounded-xl text-center">
                            <div class="text-4xl mb-4">🩺</div>
                            <h4 class="font-bold text-stone-800 mb-2">Diagnóstico Emocional</h4>
                            <p id="diagnosis-text" class="text-sm text-stone-500 italic">"Selecciona tus síntomas emocionales para ver el diagnóstico..."</p>
                            <div id="diagnosis-result" class="hidden mt-4 bg-rose-50 text-rose-800 p-4 rounded-lg text-sm font-semibold animate-pulse">
                                ¡Este mensaje es exactamente para ti!
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Author Story Teaser -->
                <div class="bg-stone-800 text-stone-200 rounded-2xl p-8 md:p-12 relative overflow-hidden">
                    <div class="relative z-10 max-w-3xl">
                        <h3 class="text-2xl font-bold text-white mb-4">De la Vulnerabilidad al Control</h3>
                        <p class="mb-6 leading-relaxed">
                            "Recuerdo mi etapa más vulnerable. Vivía con miedo constante, mi autoestima estaba por los suelos. 
                            Consulté a especialistas, probé todo... Fue en ese momento de desesperación que decidí dejar de buscar 'curas mágicas' y empezar a escuchar a mi cuerpo."
                        </p>
                        <button onclick="navigate('method')" class="text-rose-300 font-bold hover:text-rose-200 underline">Descubre cómo nació el método ➔</button>
                    </div>
                    <!-- Decorative element -->
                    <div class="absolute top-0 right-0 -mt-10 -mr-10 w-64 h-64 bg-rose-900 rounded-full opacity-20 blur-3xl"></div>
                </div>
            </section>


            <!-- SECTION: THE METHOD -->
            <section id="method" class="view-section hidden">
                <!-- Intro Context -->
                <div class="mb-8">
                    <h2 class="text-3xl font-bold text-stone-800 mb-2">El Camino hacia la Calma</h2>
                    <p class="text-stone-600">
                        Este no es un plan de dieta restrictiva. Aquí visualizamos cómo tu sensación de control y paz aumentará a lo largo de los 21 días del programa, basado en una estrategia 100% natural.
                    </p>
                </div>

                <!-- Chart Section -->
                <div class="grid lg:grid-cols-3 gap-8 mb-12">
                    <div class="lg:col-span-2 bg-white p-6 rounded-2xl shadow-sm border border-stone-100">
                        <h3 class="text-lg font-bold text-stone-800 mb-4">Proyección de Bienestar (21 Días)</h3>
                        <div class="chart-container">
                            <canvas id="progressChart"></canvas>
                        </div>
                        <p class="text-xs text-center text-stone-400 mt-2">*Proyección basada en la experiencia de usuarias</p>
                    </div>
                    
                    <div class="space-y-4">
                        <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-100 h-full flex flex-col justify-center">
                            <h3 class="text-lg font-bold text-rose-600 mb-4">Pilares del Método</h3>
                            <ul class="space-y-4">
                                <li class="flex items-start">
                                    <span class="bg-rose-100 text-rose-600 rounded-full w-6 h-6 flex items-center justify-center text-xs font-bold mr-3 mt-1">1</span>
                                    <div>
                                        <strong class="block text-stone-800">100% Natural</strong>
                                        <span class="text-sm text-stone-500">Sin procesos invasivos. Alimentación antiinflamatoria.</span>
                                    </div>
                                </li>
                                <li class="flex items-start">
                                    <span class="bg-rose-100 text-rose-600 rounded-full w-6 h-6 flex items-center justify-center text-xs font-bold mr-3 mt-1">2</span>
                                    <div>
                                        <strong class="block text-stone-800">Práctico</strong>
                                        <span class="text-sm text-stone-500">Diseñado para la vida real. Rutinas cortas y menús sencillos.</span>
                                    </div>
                                </li>
                                <li class="flex items-start">
                                    <span class="bg-rose-100 text-rose-600 rounded-full w-6 h-6 flex items-center justify-center text-xs font-bold mr-3 mt-1">3</span>
                                    <div>
                                        <strong class="block text-stone-800">21 Días Guiados</strong>
                                        <span class="text-sm text-stone-500">Claridad total. Sabrás exactamente qué hacer cada día.</span>
                                    </div>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>

                <!-- Benefits Grid -->
                <h3 class="text-xl font-bold text-stone-800 mb-6 text-center">Resultados Esperados</h3>
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-4">
                    <!-- Cards generated by JS -->
                    <div class="bg-rose-50 p-4 rounded-xl text-center hover:shadow-md transition-shadow">
                        <div class="text-3xl mb-2">🛡️</div>
                        <h4 class="font-bold text-stone-800 text-sm">Menos Brotes</h4>
                        <p class="text-xs text-stone-600 mt-1">Reduce frecuencia e intensidad.</p>
                    </div>
                    <div class="bg-rose-50 p-4 rounded-xl text-center hover:shadow-md transition-shadow">
                        <div class="text-3xl mb-2">🍽️</div>
                        <h4 class="font-bold text-stone-800 text-sm">Comer sin Miedo</h4>
                        <p class="text-xs text-stone-600 mt-1">Identifica detonantes sin estrés.</p>
                    </div>
                    <div class="bg-rose-50 p-4 rounded-xl text-center hover:shadow-md transition-shadow">
                        <div class="text-3xl mb-2">💪</div>
                        <h4 class="font-bold text-stone-800 text-sm">Inmunidad Fuerte</h4>
                        <p class="text-xs text-stone-600 mt-1">Defensa robusta desde adentro.</p>
                    </div>
                    <div class="bg-rose-50 p-4 rounded-xl text-center hover:shadow-md transition-shadow">
                        <div class="text-3xl mb-2">✨</div>
                        <h4 class="font-bold text-stone-800 text-sm">Control Total</h4>
                        <p class="text-xs text-stone-600 mt-1">Recupera tu confianza.</p>
                    </div>
                </div>
                
                <div class="text-center mt-8">
                    <button onclick="navigate('modules')" class="bg-stone-800 text-white font-bold py-2 px-6 rounded-lg hover:bg-stone-700 transition-colors">
                        Ver los Módulos ➔
                    </button>
                </div>
            </section>


            <!-- SECTION: MODULES -->
            <section id="modules" class="view-section hidden">
                <!-- Intro -->
                <div class="mb-8">
                    <h2 class="text-3xl font-bold text-stone-800 mb-2">Tu Plan de Estudios</h2>
                    <p class="text-stone-600">
                        Explora el contenido del e-book. Haz clic en cada módulo para ver los detalles de lo que aprenderás y implementarás en cada fase.
                    </p>
                </div>

                <div class="grid md:grid-cols-12 gap-6">
                    <!-- Module List (Sidebar style on desktop) -->
                    <div class="md:col-span-4 space-y-3" id="module-nav">
                        <!-- Generated by JS -->
                    </div>

                    <!-- Module Detail View -->
                    <div class="md:col-span-8">
                        <div id="module-display" class="bg-white p-8 rounded-2xl shadow-lg border border-rose-100 min-h-[400px] flex flex-col justify-center transition-all-300">
                            <!-- Content injected by JS -->
                        </div>
                    </div>
                </div>

                <!-- Bonus Banner -->
                <div class="mt-12 bg-gradient-to-r from-pink-100 to-rose-200 rounded-2xl p-6 border-2 border-rose-300 relative">
                    <div class="absolute -top-3 -right-3 bg-rose-600 text-white text-xs font-bold px-3 py-1 rounded-full shadow-md animate-bounce">
                        ¡GRATIS HOY!
                    </div>
                    <div class="flex flex-col md:flex-row items-center gap-6">
                        <div class="text-4xl">🎁</div>
                        <div>
                            <h4 class="font-bold text-rose-900 text-lg">Bono Exclusivo: Tratamiento Casero para Brotes</h4>
                            <p class="text-rose-800 text-sm mt-1">
                                Protocolo natural para Herpes y Verrugas Genitales. Recupera la calma y el alivio desde la privacidad de tu hogar. Valor real: <s>$80 USD</s>.
                            </p>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- SECTION: TESTIMONIALS / CAROUSEL -->
            <section id="testimonials" class="view-section hidden bg-white rounded-2xl p-6 md:p-12 shadow-lg border border-stone-100">
                <div class="w-full max-w-4xl mx-auto">
                    <h2 class="text-3xl font-bold text-stone-800 text-center mb-10">Testimonios en Captura: Resultados Verificados</h2>
                    
                    <div class="carousel-container relative">

                        <!-- Contenedor de Testimonios -->
                        <div id="testimonial-slider" class="flex justify-center items-center w-full">
                            
                            <!-- Testimonio 1 (Juan Gomez) -->
                            <div class="testimonial-card active w-full p-4 sm:p-6 bg-white rounded-xl transition duration-500 transform scale-100 text-center" data-index="0">
                                <img class="testimonial-image" 
                                    src="https://i.postimg.cc/bS9qXzcC/tes-1.jpg" 
                                    alt="Captura de testimonio de Juan Gomez"
                                    onerror="this.onerror=null;this.src='https://placehold.co/800x450/FCA5A5/FFFFFF?text=TESTIMONIO+JUAN+GOMEZ'">
                                <p class="text-lg font-semibold text-gray-900 mt-4">Juan Gomez</p>
                                <p class="text-sm text-stone-500 font-medium">35 años</p>
                            </div>
                            
                            <!-- Testimonio 2 (Crismar Medina) -->
                            <div class="testimonial-card hidden w-full p-4 sm:p-6 bg-white rounded-xl transition duration-500 text-center" data-index="1">
                                <img class="testimonial-image" 
                                    src="https://i.postimg.cc/SYfm0yFZ/tes-2.jpg" 
                                    alt="Captura de testimonio de Crismar Medina"
                                    onerror="this.onerror=null;this.src='https://placehold.co/800x450/FCA5A5/FFFFFF?text=TESTIMONIO+CRISMAR+MEDINA'">
                                <p class="text-lg font-semibold text-gray-900 mt-4">Crismar Medina</p>
                                <p class="text-sm text-stone-500 font-medium">28 años</p>
                            </div>

                            <!-- Testimonio 3 (Jose Reynoso) -->
                            <div class="testimonial-card hidden w-full p-4 sm:p-6 bg-white rounded-xl transition duration-500 text-center" data-index="2">
                                <img class="testimonial-image" 
                                    src="https://i.postimg.cc/Lg3mdHKx/tes-3.jpg" 
                                    alt="Captura de testimonio de Jose Reynoso"
                                    onerror="this.onerror=null;this.src='https://placehold.co/800x450/FCA5A5/FFFFFF?text=TESTIMONIO+JOSE+REYNOSO'">
                                <p class="text-lg font-semibold text-gray-900 mt-4">Jose Reynoso</p>
                                <p class="text-sm text-stone-500 font-medium">41 años</p>
                            </div>

                            <!-- Testimonio 4 (Dayana Alvarez) -->
                            <div class="testimonial-card hidden w-full p-4 sm:p-6 bg-white rounded-xl transition duration-500 text-center" data-index="3">
                                <img class="testimonial-image" 
                                    src="https://i.postimg.cc/XBknMVSx/test-4.jpg" 
                                    alt="Captura de testimonio de Dayana Alvarez"
                                    onerror="this.onerror=null;this.src='https://placehold.co/800x450/FCA5A5/FFFFFF?text=TESTIMONIO+DAYANA+ALVAREZ'">
                                <p class="text-lg font-semibold text-gray-900 mt-4">Dayana Alvarez</p>
                                <p class="text-sm text-stone-500 font-medium">24 años</p>
                            </div>

                        </div>

                        <!-- Botón Anterior (Desktop) -->
                        <button id="prev-button" class="absolute left-0 top-1/2 -translate-y-1/2 p-3 bg-white bg-opacity-80 hover:bg-opacity-100 rounded-full shadow-lg transition hidden sm:block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                            </svg>
                        </button>

                        <!-- Botón Siguiente (Desktop) -->
                        <button id="next-button" class="absolute right-0 top-1/2 -translate-y-1/2 p-3 bg-white bg-opacity-80 hover:bg-opacity-100 rounded-full shadow-lg transition hidden sm:block">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                            </svg>
                        </button>

                    </div>
                    
                    <!-- Indicadores (Dots) y Botones Móviles -->
                    <div class="flex justify-center items-center mt-8 space-x-3">
                        <!-- Botones para Móvil -->
                        <button id="prev-button-mobile" class="sm:hidden p-2 bg-rose-500 hover:bg-rose-600 text-white rounded-lg shadow transition">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                            </svg>
                        </button>

                        <!-- Puntos de Navegación -->
                        <div id="dot-indicators" class="flex space-x-2">
                            <!-- Los puntos serán generados por JavaScript -->
                        </div>

                        <button id="next-button-mobile" class="sm:hidden p-2 bg-rose-500 hover:bg-rose-600 text-white rounded-lg shadow transition">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                            </svg>
                        </button>
                    </div>

                </div>
            </section>


            <!-- SECTION: OFFER / PRICING -->
            <section id="offer" class="view-section hidden">
                <!-- Intro -->
                <div class="text-center mb-10">
                    <h2 class="text-3xl font-bold text-stone-800 mb-4">Invierte en Tu Tranquilidad</h2>
                    <p class="text-stone-600 max-w-2xl mx-auto">
                        Analiza el valor real de lo que recibes frente a la inversión simbólica de hoy. Tu paz mental no tiene precio, pero hemos hecho este plan accesible para todas.
                    </p>
                </div>

                <div class="grid lg:grid-cols-2 gap-12 items-center">
                    <!-- Value Chart -->
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-100">
                        <h3 class="text-lg font-bold text-stone-800 mb-4 text-center">Comparativa de Valor</h3>
                        <div class="chart-container">
                            <canvas id="valueChart"></canvas>
                        </div>
                    </div>

                    <!-- Pricing Card -->
                    <div class="bg-white rounded-3xl shadow-xl border border-stone-100 overflow-hidden transform hover:scale-105 transition-transform duration-300">
                        <div class="bg-stone-800 text-white p-6 text-center">
                            <h3 class="text-xl font-medium opacity-90">Oferta Especial Limitada</h3>
                            <div class="mt-4">
                                <span class="text-stone-400 line-through text-lg">$224 USD</span>
                                <div class="text-5xl font-bold text-rose-400 mt-1">$49 <span class="text-base text-stone-300 font-normal">USD</span></div>
                            </div>
                        </div>
                        <div class="p-8">
                            <ul class="space-y-4 mb-8">
                                <li class="flex items-center text-stone-700">
                                    <span class="text-green-500 mr-3">✓</span> E-book Plan de 21 Días (Valor $97)
                                </li>
                                <li class="flex items-center text-stone-700">
                                    <span class="text-green-500 mr-3">✓</span> Guías, Menús y Calendarios (Valor $47)
                                </li>
                                <li class="flex items-center text-stone-700 font-bold bg-rose-50 p-2 rounded -mx-2">
                                    <span class="text-rose-500 mr-3">🎁</span> Bono Tratamiento Casero (Valor $80)
                                </li>
                                <li class="flex items-center text-stone-700">
                                    <span class="text-green-500 mr-3">✓</span> Garantía de 7 Días
                                </li>
                            </ul>
                            <!-- ENLACE DE PAGO FINAL -->
                            <a href="https://shop.beacons.ai/eilynalbarran/ff3e881c-9199-4c6f-a89e-b0a707ce3200" target="_blank" class="w-full block bg-rose-600 text-white font-bold py-4 rounded-xl shadow-lg hover:bg-rose-700 transition-colors text-lg text-center">
                                QUIERO MI PLAN AHORA
                            </a>
                            <p class="text-center text-xs text-stone-400 mt-4">Pago seguro vía Hotmart. Acceso inmediato.</p>
                        </div>
                    </div>
                </div>

                <!-- FAQ Accordion -->
                <div class="mt-16 max-w-3xl mx-auto">
                    <h3 class="text-2xl font-bold text-stone-800 mb-6 text-center">Preguntas Frecuentes</h3>
                    <div id="faq-container" class="space-y-3">
                        <!-- Injected by JS -->
                    </div>
                </div>

                <!-- Guarantee -->
                <div class="mt-16 text-center bg-stone-100 rounded-xl p-8 max-w-2xl mx-auto">
                    <div class="text-4xl mb-4">🛡️</div>
                    <h4 class="font-bold text-stone-800 text-lg mb-2">Garantía de Satisfacción de 7 Días</h4>
                    <p class="text-stone-600 text-sm">
                        Sin riesgos. Si después de seguir el Módulo 1 sientes que el plan no es para ti, Hotmart protege tu compra. Reembolso del 100%.
                    </p>
                </div>
            </section>

        </div>

        <!-- Botón Flotante Fluorescente (Sticky) -->
        <a href="https://shop.beacons.ai/eilynalbarran/ff3e881c-9199-4c6f-a89e-b0a707ce3200" target="_blank" class="fluorescent-btn">
            <span class="text-sm md:text-base">🛒 COMPRAR PLAN $49 </span>
        </a>

    </div>

    <!-- JavaScript Logic -->
    <script>
        // --- DATA STORE ---
        
        const appData = {
            painPoints: [
                "Siento vergüenza al cancelar planes.",
                "Vivo con miedo al próximo brote.",
                "Tengo ansiedad por no saber qué comer.",
                "He probado cremas sin resultados duraderos.",
                "Me siento agotada mentalmente."
            ],
            modules: [
                {
                    id: 1,
                    title: "Módulo 1: Entendiendo tus Brotes",
                    icon: "🧠",
                    summary: "La verdad sobre el ciclo de los brotes y cómo romperlo.",
                    details: [
                        "Por qué salen y qué los activa realmente.",
                        "Cómo romper el ciclo de estrés y debilidad inmunológica.",
                        "Checklist de síntomas para autoevaluación."
                    ]
                },
                {
                    id: 2,
                    title: "Módulo 2: Detox Natural (7 Días)",
                    icon: "🍃",
                    summary: "Fase de calma: limpieza suave y desinflamación.",
                    details: [
                        "Plan de limpieza suave para desinflamar.",
                        "Recetas de alimentos 'calmantes' y protectores.",
                        "Estrategias para reducir carga viral naturalmente."
                    ]
                },
                {
                    id: 3,
                    title: "Módulo 3: Subiendo Defensas",
                    icon: "🛡️",
                    summary: "Fortalecimiento desde la raíz con nutrientes potentes.",
                    details: [
                        "Combinaciones de nutrientes antivirales.",
                        "Checklist diario de 'Súper Defensas'.",
                        "Mini reto de 7 días de reparación celular."
                    ]
                },
                {
                    id: 4,
                    title: "Módulo 4: Calendario y Rutinas",
                    icon: "📅",
                    summary: "Plan de acción de 21 días, menús y organización.",
                    details: [
                        "Menú semanal completo y organizado.",
                        "Guía de compras eficiente.",
                        "Rutinas mañaneras y nocturnas.",
                        "Plan de suplementos recomendados."
                    ]
                }
            ],
            faqs: [
                { q: "¿Se necesita experiencia en cocina o nutrición?", a: "No. El plan es sencillo y diseñado para cualquiera." },
                { q: "¿Es completamente natural?", a: "Sí. Se basa en alimentación antiinflamatoria y rutinas, sin procesos invasivos." },
                { q: "¿Qué pasa si no tengo tiempo?", a: "Las rutinas son cortas y el menú está pensado para ser eficiente." },
                { q: "¿Funciona para HSV-1 y HSV-2?", a: "Sí, al fortalecer el sistema inmune general, ayuda a manejar ambos tipos." }
            ]
        };

        // --- NAVIGATION LOGIC ---
        function navigate(viewId) {
            // Update UI State
            document.querySelectorAll('.view-section').forEach(el => el.classList.add('hidden'));
            document.getElementById(viewId).classList.remove('hidden');
            
            // Update Buttons (using nav-btn-local for the new snippet structure)
            document.querySelectorAll('.nav-btn-local').forEach(btn => {
                btn.classList.remove('active', 'bg-rose-600', 'text-white');
                btn.classList.add('hover:bg-rose-50');
            });
            const activeBtn = document.getElementById(`btn-${viewId}`);
            if(activeBtn) {
                activeBtn.classList.add('active', 'bg-rose-600', 'text-white');
                activeBtn.classList.remove('hover:bg-rose-50');
            }

            // Scroll to the content top (or top of the System.io block)
            document.getElementById(viewId).scrollIntoView({ behavior: 'smooth', block: 'start' });

            // Trigger animations or charts if needed
            if (viewId === 'method') initProgressChart();
            if (viewId === 'offer') initValueChart();
            if (viewId === 'modules') renderModuleDetail(0); // Reset to first module
            if (viewId === 'testimonials') resetCarouselInterval();
        }

        // --- SECTION: HOME / DIAGNOSIS LOGIC ---
        function initDiagnosis() {
            const container = document.getElementById('pain-points-list');
            if (!container) return; // Guard for System.io loading issues
            container.innerHTML = '';

            appData.painPoints.forEach((point, index) => {
                const div = document.createElement('div');
                div.className = 'flex items-center space-x-3 bg-stone-50 p-3 rounded-lg cursor-pointer hover:bg-rose-50 transition-colors';
                div.onclick = () => toggleCheckbox(index);
                div.innerHTML = `
                    <div class="w-6 h-6 border-2 border-rose-300 rounded flex items-center justify-center bg-white text-rose-600 font-bold transition-colors" id="cb-${index}"></div>
                    <span class="text-stone-700 text-sm select-none">${point}</span>
                `;
                container.appendChild(div);
            });
        }

        function toggleCheckbox(index) {
            const cb = document.getElementById(`cb-${index}`);
            const isChecked = cb.innerHTML !== '';
            
            if (!isChecked) {
                cb.innerHTML = '✓';
                cb.parentElement.classList.add('bg-rose-100', 'border-l-4', 'border-rose-400');
            } else {
                cb.innerHTML = '';
                cb.parentElement.classList.remove('bg-rose-100', 'border-l-4', 'border-rose-400');
            }

            // Check how many are checked
            const checkedCount = document.querySelectorAll('#pain-points-list div div:not(:empty)').length;
            const resultBox = document.getElementById('diagnosis-result');
            const resultText = document.getElementById('diagnosis-text');

            if (checkedCount > 0) {
                resultText.textContent = `Has identificado ${checkedCount} síntomas de alerta.`;
                resultBox.classList.remove('hidden');
            } else {
                resultText.textContent = "Selecciona tus síntomas emocionales para ver el diagnóstico...";
                resultBox.classList.add('hidden');
            }
        }

        // --- SECTION: MODULES LOGIC ---
        let activeModule = 0;
        function initModules() {
            const nav = document.getElementById('module-nav');
            if (!nav) return;
            nav.innerHTML = '';
            appData.modules.forEach((mod, index) => {
                const btn = document.createElement('button');
                btn.className = `w-full text-left p-4 rounded-xl border-2 transition-all duration-200 mb-2 flex items-center gap-3 ${index === 0 ? 'border-rose-400 bg-rose-50' : 'border-transparent bg-white hover:bg-stone-50'}`;
                btn.id = `mod-btn-${index}`;
                btn.onclick = () => renderModuleDetail(index);
                btn.innerHTML = `
                    <span class="text-2xl">${mod.icon}</span>
                    <div>
                        <div class="font-bold text-stone-800 text-sm">${mod.title}</div>
                    </div>
                `;
                nav.appendChild(btn);
            });
            renderModuleDetail(0);
        }

        function renderModuleDetail(index) {
            activeModule = index;
            const mod = appData.modules[index];
            const display = document.getElementById('module-display');
            
            if (!display) return;

            // Update buttons
            appData.modules.forEach((_, i) => {
                const btn = document.getElementById(`mod-btn-${i}`);
                if(!btn) return;
                if(i === index) {
                    btn.className = 'w-full text-left p-4 rounded-xl border-2 border-rose-400 bg-rose-50 mb-2 flex items-center gap-3 shadow-sm';
                } else {
                    btn.className = 'w-full text-left p-4 rounded-xl border-2 border-transparent bg-white hover:bg-stone-50 mb-2 flex items-center gap-3';
                }
            });

            // Animate content change
            display.classList.add('opacity-0');
            setTimeout(() => {
                display.innerHTML = `
                    <div class="flex items-center gap-4 mb-6">
                        <div class="text-5xl bg-rose-100 p-4 rounded-2xl">${mod.icon}</div>
                        <div>
                            <h3 class="text-2xl font-bold text-stone-800">${mod.title}</h3>
                            <p class="text-rose-600 font-medium">${mod.summary}</p>
                        </div>
                    </div>
                    <div class="bg-stone-50 rounded-xl p-6">
                        <h4 class="font-bold text-stone-700 mb-4 uppercase text-xs tracking-wider">Lo que aprenderás:</h4>
                        <ul class="space-y-3">
                            ${mod.details.map(d => `<li class="flex items-start text-stone-600 text-sm"><span class="text-rose-400 mr-2">➜</span>${d}</li>`).join('')}
                        </ul>
                    </div>
                `;
                display.classList.remove('opacity-0');
            }, 200);
        }

        // --- SECTION: FAQ LOGIC ---
        function initFAQ() {
            const container = document.getElementById('faq-container');
            if (!container) return;
            container.innerHTML = '';
            appData.faqs.forEach(item => {
                const details = document.createElement('details');
                details.className = 'group bg-white rounded-lg border border-stone-200 shadow-sm';
                details.innerHTML = `
                    <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-4 text-stone-800 group-hover:text-rose-600 transition-colors">
                        <span>${item.q}</span>
                        <span class="transition group-open:rotate-180">▼</span>
                    </summary>
                    <div class="text-stone-600 mt-0 px-4 pb-4 pt-0 text-sm leading-relaxed">
                        ${item.a}
                    </div>
                `;
                container.appendChild(details);
            });
        }

        // --- CAROUSEL LOGIC (TESTIMONIALS) ---
        let carouselCards = [];
        let currentIndex = 0;
        let intervalId = null;
        const intervalTime = 8000; // 8 segundos para rotación automática

        function initCarousel() {
            carouselCards = Array.from(document.querySelectorAll('.testimonial-card'));
            const prevButton = document.getElementById('prev-button');
            const nextButton = document.getElementById('next-button');
            const prevButtonMobile = document.getElementById('prev-button-mobile');
            const nextButtonMobile = document.getElementById('next-button-mobile');
            
            // Solo inicializar si hay tarjetas
            if (carouselCards.length === 0) return;

            // 1. Inicializar Puntos y mostrar la primera tarjeta
            generateDots();
            showTestimonial(0);

            // 2. Asignar Event Listeners
            if (prevButton) prevButton.addEventListener('click', () => { resetCarouselInterval(); prevTestimonial(); });
            if (nextButton) nextButton.addEventListener('click', () => { resetCarouselInterval(); nextTestimonial(); });
            if (prevButtonMobile) prevButtonMobile.addEventListener('click', () => { resetCarouselInterval(); prevTestimonial(); });
            if (nextButtonMobile) nextButtonMobile.addEventListener('click', () => { resetCarouselInterval(); nextTestimonial(); });

            // 3. Iniciar la rotación automática
            startCarouselInterval();
        }

        const showTestimonial = (index) => {
            if (carouselCards.length === 0) return;
            // Asegura que el índice esté dentro de los límites
            currentIndex = (index + carouselCards.length) % carouselCards.length;

            carouselCards.forEach((card, i) => {
                if (i === currentIndex) {
                    card.classList.remove('hidden');
                    card.classList.add('active');
                } else {
                    card.classList.add('hidden');
                    card.classList.remove('active');
                }
            });

            updateDots();
        };

        const updateDots = () => {
            const dotIndicators = document.getElementById('dot-indicators');
            if (!dotIndicators) return;
            const dots = dotIndicators.querySelectorAll('.dot');
            dots.forEach((dot, i) => {
                dot.classList.remove('bg-rose-600', 'scale-110');
                dot.classList.add('bg-gray-300', 'hover:bg-rose-300');
                if (i === currentIndex) {
                    dot.classList.add('bg-rose-600', 'scale-110');
                    dot.classList.remove('bg-gray-300', 'hover:bg-rose-300');
                }
            });
        };

        const generateDots = () => {
            const dotIndicators = document.getElementById('dot-indicators');
            if (!dotIndicators) return;
            dotIndicators.innerHTML = ''; // Limpiar
            carouselCards.forEach((_, i) => {
                const dot = document.createElement('button');
                dot.classList.add('dot', 'w-3', 'h-3', 'rounded-full', 'bg-gray-300', 'hover:bg-rose-300', 'transition', 'duration-300');
                dot.setAttribute('aria-label', `Ir al testimonio ${i + 1}`);
                dot.addEventListener('click', () => {
                    resetCarouselInterval();
                    showTestimonial(i);
                });
                dotIndicators.appendChild(dot);
            });
            updateDots(); // Inicializa el estado de los puntos
        };

        const nextTestimonial = () => {
            showTestimonial(currentIndex + 1);
        };

        const prevTestimonial = () => {
            showTestimonial(currentIndex - 1);
        };

        const startCarouselInterval = () => {
            if (intervalId) clearInterval(intervalId);
            intervalId = setInterval(nextTestimonial, intervalTime);
        };

        const resetCarouselInterval = () => {
            clearInterval(intervalId);
            startCarouselInterval();
        };
        // --- END CAROUSEL LOGIC ---


        // --- CHARTS LOGIC (CHART.JS) ---
        let progressChartInstance = null;
        let valueChartInstance = null;

        function initProgressChart() {
            if(progressChartInstance) return; // Only init once
            const ctx = document.getElementById('progressChart')?.getContext('2d');
            if(!ctx) return;
            
            progressChartInstance = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: ['Inicio', 'Día 7 (Detox)', 'Día 14 (Defensa)', 'Día 21 (Control)'],
                    datasets: [
                        {
                            label: 'Nivel de Ansiedad/Brotes',
                            data: [90, 60, 30, 10],
                            borderColor: '#a8a29e', // stone-400
                            borderDash: [5, 5],
                            tension: 0.4,
                            fill: false
                        },
                        {
                            label: 'Sensación de Paz y Control',
                            data: [10, 40, 70, 95],
                            borderColor: '#e11d48', // rose-600
                            backgroundColor: 'rgba(225, 29, 72, 0.1)',
                            borderWidth: 3,
                            tension: 0.4,
                            fill: true
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { position: 'bottom' },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return context.dataset.label + ': ' + context.parsed.y + '%';
                                }
                            }
                        },
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            max: 100,
                            ticks: { callback: (val) => val + '%' }
                        }
                    }
                }
            });
        }

        function initValueChart() {
            if(valueChartInstance) return;
            const ctx = document.getElementById('valueChart')?.getContext('2d');
            if(!ctx) return;

            valueChartInstance = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['E-book', 'Guías', 'Bono Extra', 'Total Real', 'Precio HOY'],
                    datasets: [{
                        label: 'Valor en USD',
                        data: [97, 47, 80, 224, 49],
                        backgroundColor: [
                            '#e7e5e4', // stone-200
                            '#e7e5e4',
                            '#fecdd3', // rose-200 (bonus)
                            '#57534e', // stone-600 (total)
                            '#e11d48'  // rose-600 (offer)
                        ],
                        borderRadius: 6
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { display: false },
                        tooltip: {
                            callbacks: {
                                label: (ctx) => `$${ctx.parsed.y} USD`
                            }
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: { callback: (val) => '$' + val }
                        }
                    }
                }
            });
        }

        // --- INITIALIZATION ---
        window.onload = function() {
            initDiagnosis();
            initModules();
            initFAQ();
            initCarousel();
            
            // Cargar la vista inicial (home)
            navigate('home');
        };

    </script>
</body>
</html>
