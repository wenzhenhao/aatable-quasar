<template>
  <q-page padding>
    <!-- content -->
    <q-select
      v-model="group"
      :options="groups"
      option-value="id"
      option-label="name"
      :label="$t('group')"
      filled
    />
  </q-page>
</template>

<script>
import { ref } from "vue";
export default {
  name: "Member",
  setup() {
    const groups = [
      { id: 1, name: "全部", value: 1, label: "asdf" },
      { id: 2, name: "ttt", value: 2, label: "qwe" },

    ];
    const group = ref(groups[0]);
    return {
      group,
      groups,
    };
  },
  created() {
    console.log(this.$t("failed"));
  },
};
</script>
