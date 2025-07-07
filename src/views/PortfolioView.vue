<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'Tombol PanicBully',
          imageUrl: 'portfolio_v2',
          status: 'Panic Bully adalah proyek sekolah yang dirancang untuk membantu siswa melaporkan tindakan perundungan dengan cepat dan aman. Website ini dilengkapi tombol panik, notifikasi real-time, dan dashboard admin.',
          tech: 'PHP Native, Foonte, Bootstrap, MySQL',
          github: 'null',
          demo: 'https://buttonpanicbully.cdcdisdiksulsel.info/'
        },
        {
          id: 2,
          name: 'Pemilihan Ketua KPM',
          imageUrl: 'sahabatmuslim',
          status: 'Website ini dibuat untuk pemilihan ketua KPM-Sulsel secara online. Dilengkapi autentikasi pemilih, perhitungan suara real-time, dan tampilan responsif.',
          tech: 'PHP Native, Tailwind, MySQL',
          github: 'null',
          demo: 'https://pemilihanketua.cdcdisdiksulsel.info/'
        },
        {
          id: 3,
          name: 'Aplikasi Konversi',
          imageUrl: 'sistekdes',
          status: 'Aplikasi web sederhana dan responsif untuk konversi suhu (Celsius, Fahrenheit, Kelvin) serta mata uang secara akurat dan cepat.',
          tech: 'Python, HTML, Tailwind',
          github: 'null',
          demo: 'https://konversi.up.railway.app/'
        },
        {
          id: 4,
          name: 'Kuis MTK Alam',
          imageUrl: 'sp2se',
          status: 'Website interaktif untuk belajar matematika dengan 3 tingkat kesulitan. Bertema alam dan dirancang agar menyenangkan dan mudah digunakan oleh siswa.',
          tech: 'HTML, Tailwind, Bootstrap, JavaScript',
          github: 'null',
          demo: 'https://mtkridwan.vercel.app/'
        },
        {
          id: 5,
          name: 'Mood Playlist Finder',
          imageUrl: 'spotify',
          status: 'Website pencarian playlist berdasarkan suasana hati (mood) menggunakan API Spotify. Didesain untuk memberikan pengalaman mendengarkan musik yang sesuai dengan emosi pengguna.',
          tech: 'Next.js, Tailwind, Spotify API',
          github: 'null',
          demo: 'https://spotify.ikhsanweb.my.id'
        },
        {
          id: 6,
          name: 'Pilketos Digital',
          imageUrl: 'pilketos',
          status: 'Platform digital untuk pemilihan OSIS di sekolah. Mendukung login siswa, rekapitulasi suara real-time, dan hasil pemilihan yang bisa dicetak.',
          tech: 'PHP Native, Bootstrap,T ailwind CSS, MySQL',
          github: 'null',
          demo: 'null'
        },
        {
          id: 7,
          name: 'Al-Qur\'an Digital',
          imageUrl: 'quran',
          status: 'Website Al-Qur\'an digital yang menampilkan daftar surah dan ayat menggunakan API. Dilengkapi fitur pencarian surah, halaman per juz, tampilan responsif, dan navigasi interaktif untuk memudahkan pembelajaran dan literasi Al-Qur\'an.',
          tech: 'PHP Native, Bootstrap, Tailwind CSS, API Quran, MySQL',
          github: 'null',
          demo: 'https://quranliterasi.cdcdisdiksulsel.info/'
        },
      ]
    };
  }
}
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>Pengalaman Proyek</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-amber-300">
            Jelajahi proyek-proyek yang pernah saya kerjakan
          </h4>
        </div>
      </header>
      <section>
        <div>
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-5 fade-zoom-in">
            <div v-for="item in items" :key="item.id">
              <div class="item-card flex flex-col items-center gap-3 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] text-amber-50 px-4 py-5">
                <div class="w-full aspect-video overflow-hidden rounded-xl">
                  <img :src="'/img/portfolio-' + item.imageUrl + '.png'" alt="Project Screenshot"
                    class="w-full h-full object-cover drop-shadow-xl rounded-xl" loading="lazy" />
                </div>
                <div class="w-full flex flex-col gap-2 text-sm md:text-base">
                  <div class="font-semibold text-lg text-center text-white">{{ item.name }}</div>
                  <div class="text-left text-xs text-[#c1c1c1]">{{ item.status }}</div>
                  <div class="text-left text-amber-300 text-sm mt-2">{{ item.tech }}</div>
                  <div class="w-full flex justify-end mt-3 gap-3 text-primary">
                    <a v-if="item.github !== 'null'" :href="item.github" target="_blank" rel="noreferrer"
                      title="Lihat repository GitHub" class="transition-all hover:text-accent">
                      <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24"
                        stroke-linecap="round" stroke-linejoin="round" height="18" width="18"
                        xmlns="http://www.w3.org/2000/svg">
                        <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 
                        6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77A5.07 5.07 0 0 0 19.91 
                        1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 
                        0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 
                        4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 
                        3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 
                        18.13V22"></path>
                      </svg>
                    </a>
                    <a v-if="item.demo !== 'null'" :href="item.demo" target="_blank" rel="noreferrer"
                      title="Lihat proyek langsung" class="transition-all hover:text-accent">
                      <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24"
                        stroke-linecap="round" stroke-linejoin="round" height="18" width="18"
                        xmlns="http://www.w3.org/2000/svg">
                        <path d="M18 13v6a2 2 0 0 1-2 
                        2H5a2 2 0 0 1-2-2V8a2 2 0 0 
                        1 2-2h6"></path>
                        <polyline points="15 3 21 3 21 9"></polyline>
                        <line x1="10" y1="14" x2="21" y2="3"></line>
                      </svg>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}
svg:hover {
  stroke: #ffdb70;
}
@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>
