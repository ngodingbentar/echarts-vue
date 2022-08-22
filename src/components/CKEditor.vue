<template>
  <div id="app">
    <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
    <div>
      <button @click="saveData">save</button>
    </div>
    <div>
      <div v-for="item in data" :key="item.id">
        <h3>{{item.title}}</h3>
        <div v-html="item.body"></div>
      </div>
    </div>
  </div>
</template>

<script>
  import ClassicEditor from '@ckeditor/ckeditor5-build-classic';

  export default {
    name: 'app',
    data() {
      return {
        editor: ClassicEditor,
        editorData: '<p>Content of the editor.</p>',
        editorConfig: {
            // The configuration of the editor.
        },
        data: [
          {
            id: 1,
            title: 'title 1',
            body: 'body 1'
          },
          {
            id: 2,
            title: 'title 2',
            body: 'body 2'
          }
        ]
      };
    },
    methods: {
      saveData() {
        this.data.push({
          id: this.data.length + 1,
          title: 'Title ' + this.data.length,
          body: this.editorData
        })
      }
    }
  }
</script>