<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Batik Air Port - Menghubungkan Langit dan Budaya Nusantara</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Lucide Icons for aesthetic icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Custom styles for the Batik theme */
        :root {
            --color-maroon: #800000;
            --color-gold: #FFD700;
        }
        .bg-maroon {
            background-color: var(--color-maroon);
        }
        .text-gold {
            color: var(--color-gold);
        }
        .border-gold {
            border-color: var(--color-gold);
        }
        .font-inter {
            font-family: 'Inter', sans-serif;
        }
        /* Style for the subtle batik pattern effect on the hero section */
        .hero-pattern {
            background-image: url("https://www.transparenttextures.com/patterns/clean-textile.png"); /* Subtle pattern */
            background-color: #800000; /* Maroon background */
            background-blend-mode: overlay;
        }
        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }
        /* Style for the details summary when expanded */
        details[open] summary {
            border-bottom: 1px solid #ddd;
            margin-bottom: 0.5rem;
        }
    </style>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'maroon': '#800000',
                        'gold': '#FFD700',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    }
                }
            }
        }

        // JavaScript for mobile navigation, icon setup, and form handling
        document.addEventListener('DOMContentLoaded', () => {
            // Function to handle the mobile menu toggle
            const menuButton = document.getElementById('menu-button');
            const mobileMenu = document.getElementById('mobile-menu');

            if (menuButton && mobileMenu) {
                menuButton.addEventListener('click', () => {
                    mobileMenu.classList.toggle('hidden');
                });
            }

            // Replace Lucide icon components with SVG elements
            lucide.createIcons();

            // Form submission simulation
            const careerForm = document.getElementById('career-application-form');
            if (careerForm) {
                careerForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    // In a real application, data would be sent to a server here.
                    // Displaying a simple success message for demonstration.
                    const successMessage = document.getElementById('success-message');
                    successMessage.classList.remove('hidden');
                    successMessage.textContent = `Aplikasi untuk posisi ${this.position.value} berhasil terkirim! Tim HR akan segera menghubungi Anda melalui email.`;
                    
                    // Reset form after 3 seconds
                    setTimeout(() => {
                        successMessage.classList.add('hidden');
                        this.reset();
                    }, 3000);
                });
            }

            // Function to pre-select position when 'Lamar Sekarang' is clicked
            document.querySelectorAll('.apply-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const positionName = e.currentTarget.getAttribute('data-position');
                    
                    // Set the selected position in the dropdown
                    document.getElementById('position').value = positionName;
                    
                    // Scroll to the form smoothly
                    const formSection = document.getElementById('application-form-section');
                    if (formSection) {
                        formSection.scrollIntoView({ behavior: 'smooth' });
                    }
                });
            });
        });
    </script>
</head>
<body class="font-sans bg-gray-50 text-gray-800">

    <!-- Navbar -->
    <header class="sticky top-0 z-50 bg-white shadow-lg">
        <nav class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex-shrink-0">
                    <!-- Tautan ke Home -->
                    <a href="#home" class="flex items-center space-x-2 text-xl font-extrabold text-maroon hover:text-red-900 transition duration-300" title="Batik Air Port - www.batikairport.com">
                        <i data-lucide="plane" class="w-6 h-6 text-gold fill-current stroke-current"></i>
                        <span>Batik Air Port</span>
                    </a>
                </div>

                <!-- Desktop Navigation Links -->
                <div class="hidden md:flex md:space-x-8">
                    <a href="#about" class="text-gray-600 hover:text-maroon transition duration-150 py-2">Tentang Kami</a>
                    <a href="#services" class="text-gray-600 hover:text-maroon transition duration-150 py-2">Layanan</a>
                    <a href="#career" class="text-gray-600 hover:text-maroon transition duration-150 py-2">Karier</a>
                    <a href="#contact" class="px-4 py-2 bg-maroon text-white font-semibold rounded-lg hover:bg-red-900 transition duration-150">Hubungi Kami</a>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden">
                    <button id="menu-button" type="button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-500 hover:text-gray-900 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-maroon">
                        <i data-lucide="menu" class="w-6 h-6"></i>
                    </button>
                </div>
            </div>
        </nav>

        <!-- Mobile Menu (Hidden by default) -->
        <div id="mobile-menu" class="md:hidden hidden bg-white shadow-xl">
            <div class="pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#about" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:bg-gray-50 hover:text-maroon">Tentang Kami</a>
                <a href="#services" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:bg-gray-50 hover:text-maroon">Layanan</a>
                <a href="#career" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:bg-gray-50 hover:text-maroon">Karier</a>
                <a href="#contact" class="block px-3 py-2 rounded-md text-base font-medium text-white bg-maroon hover:bg-red-900">Hubungi Kami</a>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main>

        <!-- 1. Halaman Utama (Home) -->
        <section id="home" class="hero-pattern text-white py-24 md:py-36 min-h-screen flex items-center rounded-b-xl shadow-2xl">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
                <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight mb-4 text-gold">
                    Selamat Datang di Batik Air Port
                </h1>
                <p class="text-xl md:text-3xl font-light max-w-4xl mx-auto mb-8">
                    Menghubungkan Langit dan Budaya Nusantara
                </p>
                <p class="max-w-3xl mx-auto text-lg mb-10 opacity-90">
                    Batik Air Port adalah perusahaan yang bergerak di bidang pelayanan penerbangan dan manajemen bandara yang mengutamakan kenyamanan, keamanan, serta sentuhan budaya Indonesia dalam setiap layanan.
                </p>
                <!-- Call-to-action buttons -->
                <div class="space-x-4">
                    <a href="#services" class="inline-flex items-center px-8 py-3 border-4 border-gold text-base font-semibold rounded-full shadow-lg bg-gold text-maroon hover:bg-yellow-500 transition duration-300 transform hover:scale-105">
                        Lihat Layanan
                    </a>
                    <a href="#contact" class="inline-flex items-center px-8 py-3 border-4 border-white text-base font-semibold rounded-full shadow-lg text-white hover:bg-white hover:text-maroon transition duration-300 transform hover:scale-105 mt-4 sm:mt-0">
                        Hubungi Kami
                    </a>
                </div>
            </div>
        </section>

        <!-- 2. Tentang Kami (About Us) -->
        <section id="about" class="py-16 md:py-24 bg-white">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <h2 class="text-maroon text-4xl font-extrabold mb-4">Tentang Kami</h2>
                    <p class="text-lg text-gray-600">Dedikasi kami untuk keunggulan dan budaya.</p>
                </div>

                <div class="grid md:grid-cols-2 gap-12 items-center">
                    <!-- Visi -->
                    <div class="p-8 bg-gray-50 rounded-xl shadow-lg border-t-4 border-maroon">
                        <i data-lucide="target" class="w-8 h-8 text-gold mb-3"></i>
                        <h3 class="text-2xl font-bold text-maroon mb-4">Visi</h3>
                        <p class="text-gray-700 text-lg">
                            Menjadi perusahaan penerbangan dan bandara terbaik yang memadukan keunggulan layanan modern dengan keindahan budaya Indonesia.
                        </p>
                    </div>

                    <!-- Misi -->
                    <div class="p-8 bg-gray-50 rounded-xl shadow-lg border-t-4 border-gold">
                        <i data-lucide="handshake" class="w-8 h-8 text-maroon mb-3"></i>
                        <h3 class="text-2xl font-bold text-maroon mb-4">Misi</h3>
                        <ul class="space-y-3 text-gray-700 list-disc list-inside text-lg">
                            <li>Memberikan pengalaman penerbangan yang nyaman dan berkelas.</li>
                            <li>Mengedepankan profesionalitas dan keramahan khas Nusantara.</li>
                            <li>Mengangkat nilai seni dan budaya Indonesia ke kancah dunia.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. Layanan (Services) -->
        <section id="services" class="py-16 md:py-24 bg-gray-100">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <h2 class="text-maroon text-4xl font-extrabold mb-4">Layanan Unggulan</h2>
                    <p class="text-lg text-gray-600">Kami menyediakan berbagai layanan terpadu untuk pengalaman terbaik Anda.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Layanan 1: Manajemen Bandara -->
                    <div class="bg-white p-6 rounded-xl shadow-xl hover:shadow-2xl transition duration-300 transform hover:-translate-y-1">
                        <i data-lucide="building-2" class="w-8 h-8 text-gold mb-4 p-1 bg-maroon rounded-full"></i>
                        <h3 class="text-xl font-semibold text-maroon mb-2">Manajemen Bandara</h3>
                        <p class="text-gray-600">Pengelolaan terminal, keamanan, dan fasilitas bandara secara menyeluruh.</p>
                    </div>

                    <!-- Layanan 2: Penerbangan Komersial -->
                    <div class="bg-white p-6 rounded-xl shadow-xl hover:shadow-2xl transition duration-300 transform hover:-translate-y-1">
                        <i data-lucide="plane-takeoff" class="w-8 h-8 text-gold mb-4 p-1 bg-maroon rounded-full"></i>
                        <h3 class="text-xl font-semibold text-maroon mb-2">Penerbangan Komersial</h3>
                        <p class="text-gray-600">Layanan penerbangan domestik dan internasional dengan armada modern.</p>
                    </div>

                    <!-- Layanan 3: Cargo & Logistik -->
                    <div class="bg-white p-6 rounded-xl shadow-xl hover:shadow-2xl transition duration-300 transform hover:-translate-y-1">
                        <i data-lucide="package-open" class="w-8 h-8 text-gold mb-4 p-1 bg-maroon rounded-full"></i>
                        <h3 class="text-xl font-semibold text-maroon mb-2">Cargo & Logistik</h3>
                        <p class="text-gray-600">Pengiriman barang cepat, aman, dan terpercaya untuk bisnis Anda.</p>
                    </div>

                    <!-- Layanan 4: Hospitality & Lounge -->
                    <div class="bg-white p-6 rounded-xl shadow-xl hover:shadow-2xl transition duration-300 transform hover:-translate-y-1">
                        <i data-lucide="coffee" class="w-8 h-8 text-gold mb-4 p-1 bg-maroon rounded-full"></i>
                        <h3 class="text-xl font-semibold text-maroon mb-2">Hospitality & Lounge</h3>
                        <p class="text-gray-600">Layanan premium dan lounge eksklusif untuk penumpang prioritas.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. Karier (Career) - Telah Diperbarui dengan Persyaratan dan Form -->
        <section id="career" class="py-16 md:py-24 bg-white">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <h2 class="text-maroon text-4xl font-extrabold mb-4">Peluang Karier: Sesuai Kompetensi MPLB</h2>
                    <p class="text-lg text-gray-600 max-w-3xl mx-auto">
                        Lihat detail persyaratan di bawah. Jika Anda memenuhi kriteria, klik 'Lamar Sekarang' untuk langsung mengisi formulir pendaftaran.
                    </p>
                </div>

                <!-- Posisi Terbuka Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">

                    <!-- Posisi 1: Customer Service / Passenger Service Officer -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="luggage" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">1. Customer Service / PSO</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Melayani penumpang (check-in, boarding, keluhan, informasi penerbangan).</li>
                                    <li>Menangani dokumen perjalanan dan tiket.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. SMK/sederajat (MPLB diutamakan).</li>
                                    <li>Berpenampilan menarik dan proporsional.</li>
                                    <li>Tinggi min. 160 cm (Wanita) / 170 cm (Pria).</li>
                                    <li>Mampu berbahasa Inggris (aktif/pasif). Bersedia kerja shift.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                                <p class="text-xs text-gold font-semibold">Komunikasi efektif, Pelayanan prima, Berorientasi solusi, Empati tinggi.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="Customer Service / PSO" class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>
                    
                    <!-- Posisi 2: Administrative Staff -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="folder" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">2. Administrative Staff</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Mengelola surat-menyurat, arsip, laporan, dan jadwal kerja.</li>
                                    <li>Membantu koordinasi antar departemen.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. SMK/sederajat (MPLB/APK diutamakan).</li>
                                    <li>Mahir MS Office (Word, Excel, PowerPoint).</li>
                                    <li>Paham kearsipan digital dan konvensional.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                                <p class="text-xs text-gold font-semibold">Teliti, Rapi, Disiplin, Mampu bekerja mandiri maupun tim.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="Administrative Staff" class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>

                    <!-- Posisi 3: Call Center Agent / Customer Care -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="phone" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">3. Call Center Agent</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Menjawab pertanyaan pelanggan via telepon dan memberikan solusi.</li>
                                    <li>Menerima keluhan dan mencatatnya dalam sistem.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. SMK/sederajat.</li>
                                    <li>Suara jelas, intonasi ramah, dan komunikatif.</li>
                                    <li>Diutamakan berpengalaman di bidang layanan pelanggan.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                                <p class="text-xs text-gold font-semibold">Komunikasi verbal prima, Kesabaran, Manajemen emosi, Problem-solving cepat.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="Call Center Agent" class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>

                    <!-- Posisi 4: Corporate Secretary Assistant -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="briefcase" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">4. Corporate Secretary Asst.</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Menyiapkan dokumen rapat, notulen, dan laporan manajemen.</li>
                                    <li>Mengatur jadwal direksi dan kegiatan perusahaan.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. D3/S1 Administrasi Perkantoran (MPLB dengan pengalaman dipertimbangkan).</li>
                                    <li>Mahir korespondensi formal.</li>
                                    <li>Menguasai etika bisnis dan protokoler.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                                <p class="text-xs text-gold font-semibold">Disiplin, Kepercayaan diri, Teliti, Kemampuan menyusun notulensi akurat.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="Corporate Secretary Asst." class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>

                    <!-- Posisi 5: Sales Administration / Ticketing Staff -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="ticket" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">5. Sales Admin / Ticketing</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Mengatur administrasi penjualan tiket dan data pelanggan.</li>
                                    <li>Membuat laporan penjualan dan rekap reservasi.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. SMK/sederajat (MPLB diutamakan).</li>
                                    <li>Familiar dengan sistem reservasi penerbangan.</li>
                                    <li>Mampu mengolah data numerik (Excel) dengan cepat dan akurat.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                                <p class="text-xs text-gold font-semibold">Orientasi target, Negosiasi dasar, Teliti dalam data, Kemampuan presentasi laporan.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="Sales Admin / Ticketing" class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>

                    <!-- Posisi 6: HR & Office Support Staff -->
                    <div class="bg-gray-50 p-6 rounded-xl border-t-4 border-maroon shadow-lg">
                        <div class="flex items-center space-x-2 mb-2">
                            <i data-lucide="users-round" class="w-6 h-6 text-maroon"></i>
                            <h4 class="text-xl font-bold text-maroon">6. HR & Office Support</h4>
                        </div>
                        <details class="text-sm text-gray-700 mt-2">
                            <summary class="font-semibold text-maroon cursor-pointer pb-2 hover:text-red-700 transition duration-150">Lihat Detail Persyaratan</summary>
                            <div class="mt-2 space-y-3">
                                <p class="font-bold text-maroon">Tugas Utama:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Mengelola data karyawan, absensi, dan dokumen kepegawaian.</li>
                                    <li>Menangani kebutuhan kantor dan korespondensi internal.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kualifikasi Dasar:</p>
                                <ul class="list-disc list-inside ml-2 space-y-1">
                                    <li>Min. SMK/sederajat (MPLB diutamakan).</li>
                                    <li>Paham dasar-dasar administrasi SDM.</li>
                                    <li>Mampu mengelola inventaris kantor.</li>
                                </ul>
                                <p class="font-bold text-maroon pt-2">Kemampuan:</p>
                            <p class="text-xs text-gold font-semibold">Kerahasiaan data, Organisasi, Komunikasi interpersonal, Multitasking.</p>
                            </div>
                        </details>
                        <a href="#application-form-section" data-position="HR & Office Support" class="apply-link mt-3 block text-gold font-semibold hover:text-yellow-600 transition duration-300">Lamar Sekarang <i data-lucide="arrow-right" class="w-4 h-4 inline ml-1"></i></a>
                    </div>

                </div>

                <!-- Formulir Pendaftaran (Application Form) -->
                <div id="application-form-section" class="max-w-3xl mx-auto mt-16 p-8 bg-gray-100 rounded-xl shadow-2xl border-t-8 border-gold">
                    <div class="text-center mb-6">
                        <h3 class="text-3xl font-bold text-maroon mb-2">Tempat Pendaftaran & Upload Berkas</h3>
                        <p class="text-gray-600">Lengkapi data Anda dan unggah CV/Resume terbaru untuk melamar.</p>
                    </div>

                    <!-- Success Message -->
                    <div id="success-message" class="hidden p-4 mb-4 text-sm text-green-700 bg-green-100 rounded-lg" role="alert">
                        <!-- Message inserted by JavaScript -->
                    </div>

                    <form id="career-application-form" action="#" method="POST" class="space-y-4">
                        
                        <!-- Pilihan Posisi -->
                        <div>
                            <label for="position" class="block text-sm font-medium text-gray-700">Posisi yang Dilamar *</label>
                            <select id="position" name="position" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 bg-white focus:border-maroon focus:ring-maroon">
                                <option value="" disabled selected>-- Pilih Posisi --</option>
                                <option value="Customer Service / PSO">1. Customer Service / PSO</option>
                                <option value="Administrative Staff">2. Administrative Staff</option>
                                <option value="Call Center Agent">3. Call Center Agent</option>
                                <option value="Corporate Secretary Asst.">4. Corporate Secretary Asst.</option>
                                <option value="Sales Admin / Ticketing">5. Sales Admin / Ticketing</option>
                                <option value="HR & Office Support">6. HR & Office Support</option>
                            </select>
                        </div>

                        <!-- Nama Lengkap -->
                        <div>
                            <label for="applicant_name" class="block text-sm font-medium text-gray-700">Nama Lengkap *</label>
                            <input type="text" id="applicant_name" name="applicant_name" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 focus:border-maroon focus:ring-maroon" placeholder="Nama sesuai KTP">
                        </div>

                        <!-- Email -->
                        <div>
                            <label for="applicant_email" class="block text-sm font-medium text-gray-700">Email Aktif *</label>
                            <input type="email" id="applicant_email" name="applicant_email" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 focus:border-maroon focus:ring-maroon" placeholder="alamat@email.com">
                        </div>
                        
                        <!-- Upload Berkas (CV/Resume) -->
                        <div>
                            <label for="resume_file" class="block text-sm font-medium text-gray-700">Upload CV/Resume (PDF/DOCX, Max 2MB) *</label>
                            <div class="mt-1 flex items-center justify-center w-full">
                                <label for="resume_file" class="flex flex-col items-center justify-center w-full h-24 border-2 border-dashed border-gray-300 rounded-lg cursor-pointer bg-white hover:bg-gray-50 transition duration-150">
                                    <div class="flex flex-col items-center justify-center pt-5 pb-6">
                                        <i data-lucide="cloud-upload" class="w-6 h-6 text-gray-500 mb-2"></i>
                                        <p class="mb-2 text-sm text-gray-500"><span class="font-semibold">Klik untuk upload</span> atau seret dan lepas</p>
                                        <p class="text-xs text-gray-500">PDF, DOCX (MAX. 2MB)</p>
                                    </div>
                                    <input id="resume_file" name="resume_file" type="file" class="hidden" accept=".pdf,.docx" required />
                                </label>
                            </div>
                        </div>

                        <button type="submit" class="w-full py-3 px-4 border border-transparent rounded-lg shadow-sm text-lg font-semibold text-maroon bg-gold hover:bg-yellow-500 transition duration-300 transform hover:scale-[1.01] mt-6">
                            Kirim Lamaran
                        </button>
                    </form>
                </div>
            </div>
        </section>

        <!-- 5. Hubungi Kami (Contact) -->
        <section id="contact" class="py-16 md:py-24 bg-gray-900 text-white">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <h2 class="text-gold text-4xl font-extrabold mb-4">Hubungi Kami</h2>
                    <p class="text-lg text-gray-300">Kami siap melayani kebutuhan dan pertanyaan Anda.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                    <!-- Contact Info -->
                    <div class="space-y-6">
                        <!-- Alamat yang Diperbarui -->
                        <div class="flex items-start space-x-4 p-4 rounded-lg bg-gray-800 shadow-xl">
                            <i data-lucide="map-pin" class="w-6 h-6 text-gold flex-shrink-0 mt-1"></i>
                            <div>
                                <p class="text-lg font-semibold text-maroon">Alamat Kantor Pusat</p>
                                <p class="text-gray-300">Jl. Bandara Ahmad Yani, Tambakharjo, Kec. Semarang Barat, Kota Semarang, Jawa Tengah 50149, Indonesia.</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4 p-4 rounded-lg bg-gray-800 shadow-xl">
                            <i data-lucide="smartphone" class="w-6 h-6 text-gold flex-shrink-0 mt-1"></i>
                            <div>
                                <p class="text-lg font-semibold text-maroon">Telepon & WhatsApp (CS)</p>
                                <!-- Nomor telepon baru -->
                                <p class="text-gray-300">083826032991</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4 p-4 rounded-lg bg-gray-800 shadow-xl">
                            <i data-lucide="mail" class="w-6 h-6 text-gold flex-shrink-0 mt-1"></i>
                            <div>
                                <p class="text-lg font-semibold text-maroon">Email</p>
                                <p class="text-gray-300">info@batikairport.com</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4 p-4 rounded-lg bg-gray-800 shadow-xl">
                            <i data-lucide="instagram" class="w-6 h-6 text-gold flex-shrink-0 mt-1"></i>
                            <div>
                                <p class="text-lg font-semibold text-maroon">Instagram</p>
                                <p class="text-gray-300">@batikairport</p>
                            </div>
                        </div>
                    </div>

                    <!-- Contact Form (Placeholder) -->
                    <div class="p-8 bg-white text-gray-800 rounded-xl shadow-2xl">
                        <h3 class="text-2xl font-bold text-maroon mb-6">Kirim Pesan</h3>
                        <form action="#" method="POST" class="space-y-4">
                            <div>
                                <label for="name" class="block text-sm font-medium text-gray-700">Nama Lengkap</label>
                                <input type="text" id="name" name="name" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 focus:border-maroon focus:ring-maroon" placeholder="Nama Anda" required>
                            </div>
                            <div>
                                <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                                <input type="email" id="email" name="email" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 focus:border-maroon focus:ring-maroon" placeholder="email@contoh.com" required>
                            </div>
                            <div>
                                <label for="message" class="block text-sm font-medium text-gray-700">Pesan</label>
                                <textarea id="message" name="message" rows="4" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 focus:border-maroon focus:ring-maroon" placeholder="Tulis pesan Anda di sini..." required></textarea>
                            </div>
                            <button type="submit" class="w-full py-3 px-4 border border-transparent rounded-lg shadow-sm text-lg font-semibold text-maroon bg-gold hover:bg-yellow-500 transition duration-300 transform hover:scale-[1.01]">
                                Kirim Pesan
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-maroon py-8 text-white">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <div class="flex flex-col md:flex-row justify-center items-center space-y-4 md:space-y-0 md:space-x-8 mb-4">
                <a href="#about" class="hover:text-gold transition duration-150">Tentang</a>
                <a href="#services" class="hover:text-gold transition duration-150">Layanan</a>
                <a href="#career" class="hover:text-gold transition duration-150">Karier</a>
                <a href="#contact" class="hover:text-gold transition duration-150">Kontak</a>
            </div>
            <p class="text-gray-300 text-sm">
                &copy; <script>document.write(new Date().getFullYear())</script> Batik Air Port. Dikelola oleh www.batikairport.com.
            </p>
        </div>
    </footer>

</body>
</html>
