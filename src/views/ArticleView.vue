<template>
  <div class="w-full md:w-3/5 mx-auto mt-5 px-4 md:px-0">
    <div class="bg-white rounded-xl p-5 md:p-10">
      <div>
        <!-- Judul -->
        <h1 class="text-xl md:text-4xl text-black font-bold leading-relaxed text-left">
          {{ title }}
        </h1>

        <!-- Tanggal Terbit -->
        <div class="mt-3 text-gray-800 text-sm text-left">
          Dipublikasikan pada <span>{{ date }}</span>
        </div>

        <!-- Garis -->
        <div class="h-[2px] w-20 md:w-1/3 my-5 md:my-10 bg-[#ffdb70]"></div>

        <!-- Gambar Thumbnail -->
        <div class="relative w-full" style="padding-top: 50%;">
          <img
            :src="image"
            class="absolute top-0 left-0 w-full h-full object-cover rounded-lg"
            alt="Thumbnail Artikel"
          />
        </div>

        <!-- Konten -->
        <div
          class="text-left text-black mt-8 leading-relaxed space-y-4"
          v-html="content"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import { useRoute } from 'vue-router';

export default {
  data() {
    return {
      route: useRoute(),
      title: '',
      image: '',
      date: '',
      content: '',
    };
  },
  mounted() {
    this.getDetails();
  },
  methods: {
    async getDetails() {
      const id = this.route.params.id;
      axios
        .get(`https://64a38c9cc3b509573b564183.mockapi.io/api/blog/all/${id}`)
        .then((response) => {
          this.title = response.data.title;
          this.image = response.data.image;
          this.date = this.formatDate(response.data.date);
          this.content = response.data.content;
        });
    },
    formatDate(dateStr) {
      const date = new Date(dateStr);
      return date.toLocaleDateString('id-ID', {
        day: 'numeric',
        month: 'long',
        year: 'numeric',
      });
    },
  },
};
</script>

<style scoped>
/* Tambahkan jika perlu efek fade atau lainnya */
</style>
