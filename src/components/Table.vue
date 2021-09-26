<template>
  <div class="tables">

    <!-- таблица  -->
    <table cellpadding="0" cellspacing="0" class="table">
      <tbody>
      <tr>
        <th class="cell-name"> User name</th>
        <th>ID</th>
      </tr>
      <tr
              v-for="(tableRow, index) in TableData"
              :key="tableRow.id"
              v-on:click="$emit('row-table-move', tableRow.name, index)"
      >
        <td class="cell-name">
          {{tableRow.name}}</td>
        <td class="cell-id">{{tableRow.id}}</td>
      </tr>
      </tbody>
    </table>
  </div>

</template>

<script>
  export default {
    name: 'Tables',

    props: {
      TableData: {
        type: Object,
        required: true,
      },
      index: Number,
    },

    methods: {
      movedTableRow(name, index) {
        this.$emit('row-table-move', name, index)
      },
    }
  }
</script>