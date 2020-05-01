<template>
  <app-content>
    <template v-slot:nav>
      <ul>
        <li v-for="(item, index) in subjects" :key="index"
        :class="{ active: index === selectedSubjectIndex}"
        @click="selectedSubjectHandler(index)">
          <a>{{item.name}}</a>
        </li>
      </ul>
    </template>
    <template v-slot:info>
      {{selectedSubject.content}}
    </template>
  </app-content>
</template>

<script>
import AppContent from "./shared/Content.vue";
export default {
  components: {
    AppContent,
  },
  props: {
    subjects: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      selectedSubjectIndex: 0
    }
  },
  methods: {
    selectedSubjectHandler(idx) {
      this.selectedSubjectIndex = idx
    }
  },
  computed: {
    selectedSubject() {
      return this.subjects[this.selectedSubjectIndex]
    }
  }
};
</script>

<style scoped></style>
