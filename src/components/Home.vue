<template>
  <v-main fluid>
    <v-form>
      <v-file-input
        label="Selecione as legendas"
        prepend-icon="mdi-message-text"
        append-outer-icon="mdi-send"
        outlined
        multiple
        chips
        v-model="files"
        @click:append-outer="processarLegendas"
      ></v-file-input>
    </v-form>
    <div class="pills">
      <Pill v-for="word in groupedWords" :key="word.name" :name="word.name" :amount="word.amount" />
    </div>
  </v-main>
</template>

<script>
import { ipcRenderer } from "electron";
import Pill from "./Pill";
export default {
  components: {
    Pill
  },
  data: function() {
    return {
      files: [],
      groupedWords: [
        { name: "you", amount: 900 },
        { name: "he", amount: 850 },
        { name: "i", amount: 1234 }
      ]
    };
  },
  methods: {
    processarLegendas() {
      ipcRenderer.send("teste", "ping");
      ipcRenderer.on("teste", (event, resp) => {
        console.log(resp);
      });
    }
  }
};
</script>

<style>
.pills {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>