<template>
  <div>
    <div class="d-flex justify-center"><slot name="header" /></div>
    <table class="d-flex flex-column justify-center">
      <thead>
        <tr class="green white--text">
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
        <tr>
          <slot name="bodyappend" />
        </tr>
      </tbody>
    </table>
    <div class="d-flx justify-center"><slot name="footer" /></div>
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

<style lang="scss" scoped></style>
