<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
      </q-toolbar>
      <div class="q-px-md q-mb-md">
        <div class="text-h3">Today</div>
        <div class="text-subtitle1">{{ todaysDate }}</div>
      </div>
      <q-img src="~/assets/money.jpg" class="header-image absolute-top" />
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      :width="250"
      :breakpoint="600"
    >
      <q-scroll-area
        style="
          height: calc(100% - 163px);
          margin-top: 163px;
          border-right: 1px solid #ddd;
        "
      >
        <q-list padding>
          <q-item to="/" exact clickable v-ripple>
            <q-item-section avatar> <q-icon name="list" /> </q-item-section>

            <q-item-section> Todo </q-item-section>
          </q-item>

          <q-item to="/help" exact clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="help" />
            </q-item-section>

            <q-item-section> Help </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>

      <q-img
        class="absolute-top"
        src="~/assets/money.jpg"
        style="height: 163px"
      >
        <div class="absolute-bottom bg-transparent text-dark">
          <q-avatar size="56px" class="q-mb-sm">
            <img
              src="https://avatars.githubusercontent.com/u/44151951?s=96&v=4"
            />
          </q-avatar>
          <div class="text-weight-bold">Swee Giap</div>
          <div>@sweegiap</div>
        </div>
      </q-img>
    </q-drawer>

    <q-page-container>
      <router-view v-slot="{ Component }">
        <keep-alive>
          <component
            :is="Component"
            :key="$route.name"
            v-if="!$q.platform.is.bex"
          ></component>
        </keep-alive>
        <component
          :is="Component"
          v-if="$q.platform.is.bex"
          :key="$route.name"
        ></component>
      </router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from "quasar";
import { defineComponent, ref } from "vue";

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

  computed: {
    todaysDate() {
      return date.formatDate(Date.now(), "dddd -  D MMM, YYYY");
    },
  },
});
</script>

<style lang="scss">
.header-image {
  height: 100%;
  z-index: -1;
  opacity: 0.2;
  filter: grayscale(100%);
}
</style>
