<template>
  <q-layout view="lHr lpR fFf">
    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title class="text-weight-bold">
          {{ $route.name }}
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      bordered
      :width="283"
      >

      <q-icon name="fas fa-dove" size="lg" color="primary" class="q-pa-md" />

      <q-item
        to="/"
        clickable
        v-ripple
        exact
      >
        <q-item-section avatar>
          <q-icon name="home" size="md" />
        </q-item-section>

        <q-item-section class="text-h6 text-weight-bold">Home</q-item-section>
      </q-item>

      <q-item
        to="/about"
        clickable
        v-ripple
        exact
      >
        <q-item-section avatar>
          <q-icon name="help" size="md" />
        </q-item-section>

        <q-item-section class="text-h6 text-weight-bold">About</q-item-section>
      </q-item>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
          <q-input
            class="q-ma-md"
            rounded
            outlined
            placeholder="search the site"
            dense
          >

          <template v-slot:prepend>
            <q-icon name="search" />
          </template>
        </q-input>

        <q-list padding>
          <q-item>
            <q-item-section>
              <q-item-label class="text-grey" overline>World News</q-item-label>
              <q-item-label class="text-weight-bold">2023 is definitely going to be our year!</q-item-label>
              <q-item-label caption>"Woman says next year will be her year every single NYE"</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>

        <q-list padding>
          <q-item>
            <q-item-section>
              <q-item-label class="text-grey" overline>Education</q-item-label>
              <q-item-label class="text-weight-bold">Something is happening somewhere!</q-item-label>
              <q-item-label caption>Stay tuned for the turn of events that something is definitely happening somewhere</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>

        <q-list padding>
          <q-item>
            <q-item-section>
              <q-item-label class="text-grey" overline>Manifesting</q-item-label>
              <q-item-label class="text-weight-bold">Happiness for all!</q-item-label>
              <q-item-label caption>May 2023 bring joy and happiness for everyone in the new year</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>

    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const leftDrawerOpen = ref(false);
    const rightDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },

      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
};
</script>
