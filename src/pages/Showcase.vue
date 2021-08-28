<template>
  <q-page class="flex flex-center">
    <div>
      <q-toggle v-model="drawerState" color="green" />
    </div>
  </q-page>
</template>

<script>
import { defineComponent, computed } from "vue";
import { userStore } from "vuex";

export default defineComponent({
  name: "Showcase",
  setup() {
    const $store = useStore();
    const drawerState = computed({
      get: () => $store.state.showcase.drawerState,
      set: (val) => {
        $store.commit("showcase/updateDrawerState", val);
      },
    });

    setInterval(() => {
      console.log('drawerState', drawerState.value)
    }, 1000)
    return {
      drawerState,
    };
  },
});
</script>
