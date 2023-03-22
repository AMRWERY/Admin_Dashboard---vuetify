<template>
  <div class="dashboard">
    <v-subheader class="d-flex justify-space-between align-center">
      <h3>Dashboard</h3>
      <v-btn variant="flat" color="success" rounded="lg">View Orders</v-btn>
    </v-subheader>
    <v-row>
      <v-col lg="8" cols="12">
        <v-alert type="success" variant="tonal">
          <strong>Login Successfully,</strong> Good Morning
        </v-alert>

        <v-row>
          <v-col lg="6" cols="12" v-for="activity in activities" :key="activity">
            <v-card elevation="2" rounded="lg" class="mt-6">
              <v-card-text class="d-flex justify-space-between align-center">
                <div>
                  <strong class="text-blue">{{ activity.title }}</strong>
                  <br>
                  <small>Last 2 Weeks</small>
                </div>
                <v-avatar :color="activity.color" variant="tonal" size="60">
                  <span class="text-black">{{ activity.amount }}</span>
                </v-avatar>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-col>

      <v-col lg="4" cols="12">
        <TimeLine />
      </v-col>
    </v-row>
    <v-row>
      <v-col lg="12">
          <DashboardTable />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import TimeLine from '@/views/TimeLine.vue';
import DashboardTable from './DashboardTable.vue';

export default {
  components: { TimeLine, DashboardTable },

  data() {
    return {
      activities: [
        { title: 'Total products', color: 'red', amount: 1234 },
        { title: 'Total Category', color: 'purple', amount: 32 },
        { title: 'Total Orders', color: 'indigo', amount: 2468 },
        { title: 'Pending Orders', color: 'green', amount: 357 }
      ]
    }
  }
}
</script>

