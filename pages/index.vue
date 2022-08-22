<template>
  <div class="w-1/2 mx-auto my-20">
    <!-- <button
      class="bg-red-500 p-3 text-white"
      v-on:click="carregarLista()"
    >
      carregarLista
    </button> -->
    <h1 class="text-3xl font-semibold text-red-600">
      {{ titulo }}
    </h1>

    <div
      v-for="pok in lista"
      :key="pok.name"
      class="max-w-sm rounded overflow-hidden shadow-lg"
    >
      <img
        class="w-full"
        src="/img/card-top.jpg"
        alt="Sunset in the mountains"
      />
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">
          {{ pok.name }}
        </div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus
          quia, nulla! Maiores et perferendis eaque, exercitationem praesentium
          nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="
            inline-block
            bg-gray-200
            rounded-full
            px-3
            py-1
            text-sm
            font-semibold
            text-gray-700
            mr-2
            mb-2
          "
          >#grass</span
        >
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      lista: [],
      titulo: "Estudo Nuxt",
    };
  },

  created: function () {
    let url = "https://pokeapi.co/api/v2/pokemon?limit=3";
    axios.get(url).then((res) => {
      this.lista = res.data.results;
      console.warn(this.lista);
    });
  },

  // methods: {
  //   carregarLista() {
  //     let url = "https://pokeapi.co/api/v2/pokemon?limit=3";
  //     axios.get(url).then((res) => {
  //       this.lista = res.data.results;
  //       console.warn(this.lista);
  //     });
  //   },
  // },
};
</script>
