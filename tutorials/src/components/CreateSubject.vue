<template>
  <app-content>
    <template v-slot:nav>
      <ul>
        <li
          v-for="(item, index) in subjects"
          :key="index"
          :class="{ active: index === selectedSubjectIndex }"
          @click="selectedSubjectHandler(index)"
        >
          <a>{{ item.name }}</a>
        </li>
      </ul>
    </template>
    <template v-slot:info>
      <div class="form-group">
        <input placeholder="Technology subject..." type="text" id="subject" v-model="subject" />
      </div>
      <select name="technologies" id="technologies" v-model="technology">
        <option :value="null" selected>Select a technology...</option>
        <option v-for="item in technologies" :key="item.id" :value="item.id">{{item.name}}</option>
      </select>
      <vue-editor v-model="htmlContent" />
      <button class="btn" @click="createSubjectHandler()">Create</button>
      <h3>Content preview</h3>
      {{$data}}
      <div class="content-preview"></div>
    </template>
  </app-content>
</template>

<script>
import AppContent from './shared/Content.vue'
import { VueEditor } from 'vue2-editor'
export default {
  components: {
    AppContent,
    VueEditor,
  },
  props: {
    subjects: {
      type: Array,
      required: true,
    },
    technologies: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      selectedSubjectIndex: 0,
      htmlContent: '',
      technology: null,
      subject: ''
    }
  },
  methods: {
    selectedSubjectHandler(idx) {
      this.selectedSubjectIndex = idx
    },
    createSubjectHandler() {
        this.$emit('create')
    }
  },
  computed: {
    selectedSubject() {
      return this.subjects[this.selectedSubjectIndex]
    },
  },
}
</script>

<style scoped></style>
