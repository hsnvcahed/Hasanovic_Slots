<template>
  <div>
    <DataTable :items="desserts" :headers="headers">
      <template v-slot:header>
        <h2>Watch What You Eat!</h2>
      </template>
      <template v-slot:footer> Created 2021 by Robert Baumgartner </template>
      <template v-slot:bodyappend>
        <tr class="last-row">
          <td>Total</td>
          <td>{{ totalCalories }}</td>
          <td>{{ totalFat }}</td>
          <td>{{ totalCarbs }}</td>
          <td>{{ totalProtein }}</td>
          <td></td>
        </tr>
      </template>
    </DataTable>
    <AppLayout v-if="false">
      <template v-slot:header>
        I was made with Vue slots!
      </template>
      <template v-slot:default>
        <AppButton><img src="home.svg" /> Home</AppButton>

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
      </template>
      <template v-slot:footer>
        By Robert Baumgartner
      </template>
    </AppLayout>
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
};
</script>

<style lang="scss" scoped></style>
