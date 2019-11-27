<template>
  <div>
    <div class="row pb-2">
      <div class="col">
        <h5>Selected item:</h5>
        <pre>{{ selected }}</pre>
      </div>
    </div>
    <v-select-box v-model="selected" :options="options"></v-select-box>
  </div>
</template>

<script>
  import VSelectBox from 'v-select-box'

  export default {
    name: 'app',
    components: {
      VSelectBox
    },
    methods: {
      load (params) {
        console.log(params)
        const { q, page } = params
        const items = []

        if (q === 'a') {
          if (page === 1) {
            items.push({ id: 1, text: 'item a1' })
            items.push({ id: 2, text: 'item a2' })
            items.push({ id: 3, text: 'item a3' })
            items.push({ id: 4, text: 'item a4' })
            items.push({ id: 5, text: 'item a5' })
            items.push({ id: 6, text: 'item a6' })
            items.push({ id: 7, text: 'item a7' })
            items.push({ id: 8, text: 'item a8' })
            items.push({ id: 9, text: 'item a9' })
            items.push({ id: 10, text: 'item a10' })
          }

          if (page === 2) {
            items.push({ id: 1, text: 'item a11' })
            items.push({ id: 2, text: 'item a12' })
            items.push({ id: 3, text: 'item a13' })
            items.push({ id: 4, text: 'item a14' })
            items.push({ id: 5, text: 'item a15' })
            items.push({ id: 6, text: 'item a16' })
            items.push({ id: 7, text: 'item a17' })
            items.push({ id: 8, text: 'item a18' })
            items.push({ id: 9, text: 'item a19' })
            items.push({ id: 10, text: 'item a20' })
          }

          if (page === 3) {
            items.push({ id: 1, text: 'item a21' })
            items.push({ id: 2, text: 'item a22' })
            items.push({ id: 3, text: 'item a23' })
            items.push({ id: 4, text: 'item a24' })
            items.push({ id: 5, text: 'item a25' })
            items.push({ id: 6, text: 'item a26' })
            items.push({ id: 7, text: 'item a27' })
            items.push({ id: 8, text: 'item a28' })
            items.push({ id: 9, text: 'item a29' })
            items.push({ id: 10, text: 'item a30' })
          }
        }

        const result = { page, pageCount: 3, pageSize: 10, items }
        return Promise.resolve(result)
      }
    },
    data () {
      return {
        selected: [],
        options: {
          load: this.load,
          locale: 'enUS',
          placeholder: 'type "a"',
          multi: true
        }
      }
    }
  }
</script>

<style>
  body {
    padding: 1rem;
  }
</style>