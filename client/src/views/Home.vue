<template>
  <div>
    <DataTable :items="desserts" :headers="headers" v-if="false">
      <template v-slot:header>
        <h2>Watch What You Eat!</h2>
      </template>
      <template v-slot:footer> Created 2021 by Robert Baumgartner </template>
      <template v-slot:bodyappend>
        <tr class="last-row">
          <td style="width:200px">Total</td>
          <td style="width:200px">{{ totalCalories }}</td>
          <td style="width:200px">{{ totalFat }}</td>
          <td style="width:200px">{{ totalCarbs }}</td>
          <td style="width:200px">{{ totalProtein }}</td>
          <td style="width:200px"></td>
        </tr>
      </template>
    </DataTable>
    <AppLayout v-if="true">
      <template v-slot:default>
        <AppButton><img src="home.svg" /> Home</AppButton>
      </template>
      <template v-slot:footer>
        By Robert Baumgartner |
        <span class="red ma-3 pa-3">
          Antwort: Nein, die Reihenfolge in der die Slots angegeben werden macht keinen Unterschied
          Baumgartner
        </span>
      </template>
      <template v-slot:header>
        I was made with Vue slots!
      </template>
    </AppLayout>
    <div style="display:flex" v-if="false">
      <Sheet style="margin-left:20px">
        <h3>Memo to myself</h3>
        <p>Always prepare for PLFs in time!</p>
        <img src="info.svg" width="80px" />
      </Sheet>
      <Sheet style="margin-left:20px">
        <p>INSY, SEW and Webtechnologies are our favorite subjects!</p>
        <span style="font-style: italic">Starkschwitz Fiedler, Jan Schreck</span>
        <p>Wish i was there!</p>
        <span style="font-style: italic">E. Wahn</span>
      </Sheet>
    </div>
  </div>
</template>

<script>
import AppLayout from '@/components/AppLayout.vue';
import AppButton from '@/components/AppButton.vue';
import Sheet from '@/components/Sheet.vue';
import DataTable from '@/components/DataTable.vue';

export default {
  data() {
    return {
      desserts: [
        ['Cake', 40, 50, 30, 10, 10],
        ['Another Cake', 70, 20, 60, 60, 6],
        ['More Cake', 70, 20, 60, 60, 6],
        ['Why is there so much Cake', 70, 20, 60, 60, 6],
      ],
      headers: ['Dessert', 'Calories', 'Fat', 'Carbs', 'Protein', 'Iron'],
    };
  },
  components: {
    Sheet,
    AppLayout,
    AppButton,
    DataTable,
  },
  computed: {
    totalCalories() {
      let res = 0;
      this.desserts.forEach((d) => (res += d[1]));
      return res;
    },
    totalFat() {
      let res = 0;
      this.desserts.forEach((d) => (res += d[2]));
      return res;
    },
    totalCarbs() {
      let res = 0;
      this.desserts.forEach((d) => (res += d[3]));
      return res;
    },
    totalProtein() {
      let res = 0;
      this.desserts.forEach((d) => (res += d[4]));
      return res;
    },
  },
};
</script>

<style lang="scss" scoped></style>
