<template>
  <div>Soy pagina uno</div>
  <div class="text-h3">{{ store.num }}</div>
  <q-btn label="Aumentar" @click="store.num++" />
  <q-btn label="Disminuir" @click="store.num--" />
</template>
<script>
import { useCounterStore } from "stores/example-store";
export default {
  name: "UnoPage",
  data() {
    return {
      store: useCounterStore(),
    };
  },
};
</script>
