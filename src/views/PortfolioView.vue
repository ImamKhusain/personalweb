<script>
export default {
  data() {
    return {
      activeTab: 1,
      showModal: false,
      modalImage: "",
      items: [
        {
          id: 1,
          name: "SERTIFIKAT JUARA 1",
          imageUrl: "Sertifikat-Juara1",
          status:
            "Physiotherapy Festival Anniversary event on Saturday, September 17, 2022 by Universitas Pembangunan Nasional “Veteran” Jakarta.",
          tech: "CorelDraw, Adobe Ilustrator",
          github: "null",
          demo: "null",
        },
        {
          id: 2,
          name: "SERTIFIKAT PESERTA LOMBA",
          imageUrl: "Sertifikat1_2022",
          status: "Competition MELAR 2022 Digital Poster Competition.",
          tech: "CorelDraw, Adobe Ilustrator",
          github: "null",
          demo: "null",
        },
        {
          id: 3,
          name: "SERTIFIKAT PESERTA LOMBA",
          imageUrl: "Sertifikat2_2022",
          status:
            "Graphic Design Competition by UKM Peduli Kemanusiaan UNESA on October 1 - November 13, 2022.",
          tech: "CorelDraw, Adobe Ilustrator",
          github: "null",
          demo: "null",
        },
        {
          id: 4,
          name: "SERTIFIKAT PESERTA LOMBA",
          imageUrl: "Sertifikat3_2022",
          status:
            "Infographic Competition of Agribusiness Expo Competitions 2022 organized by Faculty of Agriculture, Universitas Gadjah Mada on Saturday, September 11, 2022.",
          tech: "CorelDraw, Adobe Ilustrator",
          github: "null",
          demo: "null",
        },
        {
          id: 5,
          name: "SERTIFIKAT WEB DEVELOPMENT FOR BEGINNER",
          imageUrl: "Sertifikat1_2024",
          status:
            "Mini Bootcamp Web Development For Beginner on February 15, 2024.",
          tech: "HTML, CSS, JavaScript",
          github: "null",
          demo: "null",
        },
        {
          id: 6,
          name: "SERTIFIKAT PESERTA LOMBA",
          imageUrl: "Sertifikat2_2024",
          status:
            "Participating The Design Grafis Slash National Competition 2024.",
          tech: "CorelDraw, Adobe Ilustrator",
          github: "null",
          demo: "null",
        },
        {
          id: 7,
          name: "SERTIFIKAT BOOTCAMP SCHEMAICS",
          imageUrl: "Sertifikat3_2024",
          status:
            "Bootcamp and Seminar of Technology 2024 organized by Department of Informatics Engineering, Institut Teknologi Sepuluh Nopember.",
          tech: "HTML, CSS, JavaScript",
          github: "null",
          demo: "null",
        },
        {
          id: 8,
          name: "PROJECT MANAGER",
          imageUrl: "PM1_2025",
          status:
            "Project Manager in the creation of the smada madiun alumni association website which was carried out in March 2025.",
          tech: "CorelDraw, Adobe Ilustrator, Figma",
          github: "null",
          demo: "https://ikasda-madiun.com/",
        },
        {
          id: 9,
          name: "USER INTERFACE APK STRIDEHUB",
          imageUrl: "StrideHub",
          status:
            "Make the final project of the shoe store application design whose store name is StrideHub in 2024.",
          tech: "CorelDraw, Adobe Ilustrator, Figma",
          github: "null",
          demo: "https://www.figma.com/proto/E7Hqwp7gyrAT9UgOl5lXC1/Project-TokoOnline-StrideHub?node-id=1008-602&p=f&t=CEhIDbGyj4XsmBVi-0&scaling=scale-down&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=1008%3A1007&show-proto-sidebar=1",
        },
      ],
    };
  },
  methods: {
    openModal(imagePath) {
      this.modalImage = imagePath;
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
      this.modalImage = "";
    },
  },
};
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div
          class="text-2xl font-bold text-white mb-10 title-section flex items-center justify-center flex-col"
        >
          <h4>Past Project Experience</h4>
          <h4
            class="text-base font-medium text-transparent bg-clip-text bg-[#6FE6FC] from-slate-100 to-amber-300 drop-shadow-md"
          >
            Explore the projects I've worked on so far
          </h4>
        </div>
      </header>

      <section>
        <div>
          <div
            class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 xl:grid-cols-3 fade-zoom-in"
          >
            <div v-for="item in items" :key="item.id" class="h-full">
              <div
                class="item-card h-full flex flex-col justify-between items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-amber-50 px-5 py-5"
              >
                <!-- Gambar -->
                <div
                  class="flex items-center justify-center w-full cursor-pointer"
                  @click="openModal('/img/' + item.imageUrl + '.jpg')"
                >
                  <img
                    :src="'/img/' + item.imageUrl + '.jpg'"
                    alt="project-image"
                    class="rounded-xl object-cover w-full h-48 transition-transform hover:scale-105"
                  />
                </div>

                <!-- Detail -->
                <div
                  class="w-full flex flex-col justify-between gap-2 h-full text-sm md:text-base lg:text-lg"
                >
                  <div
                    class="title-text font-medium text-secondary text-center min-h-[48px] md:min-h-[56px] line-clamp-2"
                  >
                    {{ item.name }}
                  </div>

                  <div
                    class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm min-h-[60px] md:min-h-[80px] line-clamp-3"
                  >
                    {{ item.status }}
                  </div>

                  <div
                    class="w-full mt-4 text-sm text-left text-[#6FE6FC] min-h-[24px]"
                  >
                    {{ item.tech }}
                  </div>

                  <div class="w-full flex justify-end">
                    <div
                      class="flex cursor-pointer items-end gap-2 text-primary"
                    >
                      <!-- GitHub -->
                      <a
                        v-if="item.github !== 'null'"
                        :href="item.github"
                        target="_blank"
                        rel="noreferrer"
                        title="View github repository"
                        class="transition-all hover:text-accent"
                      >
                        <svg
                          stroke="currentColor"
                          fill="none"
                          stroke-width="2"
                          viewBox="0 0 24 24"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          height="16"
                          width="16"
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                          />
                        </svg>
                      </a>

                      <!-- Demo -->
                      <a
                        v-if="item.demo !== 'null'"
                        :href="item.demo"
                        target="_blank"
                        rel="noreferrer"
                        title="View finished project"
                        class="transition-all hover:text-accent"
                      >
                        <svg
                          stroke="currentColor"
                          fill="none"
                          stroke-width="2"
                          viewBox="0 0 24 24"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          height="18"
                          width="18"
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path
                            d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                          />
                          <polyline points="15 3 21 3 21 9" />
                          <line x1="10" y1="14" x2="21" y2="3" />
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>

    <!-- MODAL IMAGE -->
    <div
      v-if="showModal"
      class="fixed inset-0 z-50 bg-black bg-opacity-80 flex items-center justify-center"
    >
      <div class="relative max-w-4xl w-full p-4">
        <img
          :src="modalImage"
          alt="Zoom Image"
          class="w-full max-h-[80vh] object-contain rounded-xl shadow-lg"
        />
        <button
          @click="closeModal"
          class="absolute top-2 right-2 text-white text-2xl bg-red-600 hover:bg-red-700 w-8 h-8 flex items-center justify-center rounded-full"
          aria-label="Close"
        >
          &times;
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
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
