<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Quasar App </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>
        <q-item clickable v-ripple to="/">
          <q-item-section avatar>
            <q-icon color="primary" name="bluetooth" />
          </q-item-section>

          <q-item-section>Icon as avatar</q-item-section>
        </q-item>

        <q-item clickable v-ripple to="/dos">
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="bluetooth" />
          </q-item-section>

          <q-item-section>Avatar-type icon</q-item-section>
        </q-item>

        <q-item clickable v-ripple to="/tres">
          <q-item-section avatar>
            <q-avatar
              rounded
              color="purple"
              text-color="white"
              icon="bluetooth"
            />
          </q-item-section>

          <q-item-section>Rounded avatar-type icon</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

export default defineComponent({
  name: "MainLayout",

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
