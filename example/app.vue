<template>
  <div
    id="app"
    class="container w-full md:w-4/5 xl:w-3/5  mx-auto px-2"
  >
    <!-- Using the MadVueDatatable component -->
    <mad-vue-datatable
      ref="table"
      :action="true"
      :column-filtering="true"
      :dtfields="dtfields"
      url="/json.txt"
      @testing="doTesting"
    >
    <template slot-scope="props">
    <button
    class="group relative w-full flex justify-center py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
    data-action="testing"
    >
    {{ props.ctx.data.name }}
    </button>
    </template>
    </mad-vue-datatable>
  </div>
</template>

<script>
import MadVueDatatable from '../src'
export default {
  name: 'App',
  components: { MadVueDatatable },
  data() {
    const vm = this
    return {
      dtfields: {
        name: { label: 'Name', sortable: true, searchable: true, defaultOrder: 'desc' },
        name2: { label: 'Name', data:'name', sortable: true, searchable: true, defaultOrder: 'desc' },
        name3: { label: 'Name', data:'name', sortable: true, searchable: true, defaultOrder: 'desc' },
        name4: { label: 'Name', data:'name', sortable: true, searchable: true, defaultOrder: 'desc' },
        name5: { label: 'Name', data:'name', sortable: true, searchable: true, defaultOrder: 'desc' },
        name6: { label: 'Name', data:'name', sortable: true, searchable: true, defaultOrder: 'desc' }
      },
    }
  },
  methods: {
    doTesting(data){
      console.log(data)
    }
  }
}
</script>
