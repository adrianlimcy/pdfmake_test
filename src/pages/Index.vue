<template>
  <q-page class="flex flex-center">
    <q-btn @click="generate" label="This will generate the sample pdf"/>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {}
  },
  methods: {
    generate () {
      var pdfMake = require('pdfmake/build/pdfmake.js')
      var pdfFonts = require('pdfmake/build/vfs_fonts')
      pdfMake.vfs = pdfFonts.pdfMake.vfs
      var docDefinition = {
        content: 'This is an sample PDF printed with pdfMake'
      }
      pdfMake.createPdf(docDefinition).download('optionalName.pdf')
    }
  }
}
</script>
