<template>
  <div class="data-table d-flex justify-center flex-wrap">
    <div class="d-flex justify-center"><slot name="header" /></div>
    <table class="d-flex flex-column justify-center">
      <thead>
        <tr>
          <th style="width:200px" v-for="(el, id) in headers" :key="id">
            {{ el }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, idd) in items" :key="idd">
          <td style="width:200px;padding:10px" v-for="(itemprop, iddd) in item" :key="iddd">
            {{ itemprop }}
          </td>
        </tr>
        <hr />
        <tr class="font-weight-bold">
          <slot name="bodyappend" />
        </tr>
      </tbody>
    </table>
    <div class="d-flex justify-center"><slot name="footer" /></div>
  </div>
</template>

<script>
export default {
  props: {
    headers: {
      type: Array,
    },
    items: {
      type: Array,
    },
  },
};
</script>

<style lang="css" scoped>
.data-table {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  margin: 40px;
  border-collapse: collapse;
  font-size: 0.9em;
  font-family: sans-serif;
  min-width: 400px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.data-table td,
th {
  text-align: left;
}
.data-table footer {
  margin: 30px 0 30px 0;
  font-style: italic;
}
.data-table thead tr {
  background-color: #009879;
  color: #ffffff;
  text-align: left;
}
.data-table th,
.data-table td {
  padding: 12px 15px;
}
.data-table tbody tr {
  border-bottom: 1px solid #dddddd;
}
.data-table tbody tr:nth-of-type(even) {
  background-color: #f3f3f3;
}
</style>
