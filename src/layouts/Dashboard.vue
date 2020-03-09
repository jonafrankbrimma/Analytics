<template>
  <q-layout view="hHh lpR fFf">

    <q-header class="bg-primary text-white">
      <q-toolbar>
        <q-btn size="18px" @click="left = !left" flat round dense icon="pie_chart" />
        <q-toolbar-title @click="left = !left">Encompass Analytics</q-toolbar-title>
        <q-btn size="18px" flat round dense icon="account_circle">
          <q-menu>
            <div class="row no-wrap q-pa-md">
              <div class="column">
                <div class="text-h6 q-mb-md">Settings</div>
                <q-toggle v-model="a" label="Use Mobile Data" />
                <q-toggle v-model="b" label="Dark Mode" />
              </div>
              <q-separator vertical inset class="q-mx-lg" />
              <div class="column items-center">
                <q-avatar size="72px">
                  <img src="https://cdn.quasar.dev/img/avatar4.jpg">
                </q-avatar>
                <div class="text-subtitle1 q-mt-md q-mb-xs">John Doe</div>
                <q-btn
                  color="primary"
                  label="Logout"
                  push
                  size="sm"
                  v-close-popup
                />
              </div>
            </div>
          </q-menu>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="left" side="left">
      <q-list bordered>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="multiline_chart" />
          </q-item-section>
          <q-item-section class="text-white text-bold">Dashboard</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="notes" />
          </q-item-section>
          <q-item-section class="text-white text-bold">Statistics</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar color="teal" text-color="white" icon="exit_to_app" />
          </q-item-section>
          <q-item-section class="text-white text-bold">Logout</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="right" side="right">
      <div class="q-pa-sm">
        <div class="row justify-between">
          <div class="col-10 text-bold" style="font-size: 18px">My Work Queue (19)</div>
          <div class="col-2 text-right">
            <q-icon size="24px" color="green" name="fullscreen" />
          </div>
        </div>
        <div class="row justify-end q-pa-sm">
          <q-btn color="green" size="md" icon="filter_list" label="Filter By" />
        </div>
        <q-list>
          <q-card flat bordered class="qu-card">
            <q-card-section class="position-relative">
              <div class="text-h6">John Doe</div>
              <q-icon class="qu-icon" size="20px" name="warning" color="red"/>
            </q-card-section>
            <q-separator inset />
            <q-card-section class="q-pb-none text-grey">New Loans Approval</q-card-section>
            <q-card-section class="q-pt-none text-red">01/02/2020</q-card-section>
          </q-card>
          <q-card flat bordered class="qu-card">
            <q-card-section class="position-relative">
              <div class="text-h6">Jane Mae</div>
              <q-icon class="qu-icon" size="20px" name="date_range" color="green"/>
            </q-card-section>
            <q-separator inset />
            <q-card-section class="q-pb-none text-grey">Anniversary</q-card-section>
            <q-card-section class="q-pt-none text-red">04/03/2020</q-card-section>
          </q-card>
          <q-card flat bordered class="qu-card">
            <q-card-section class="position-relative">
              <div class="text-h6">Kevin Heart</div>
              <q-icon class="qu-icon" size="20px" name="warning" color="red"/>
            </q-card-section>
            <q-separator inset />
            <q-card-section class="q-pb-none text-grey">New Loans Approval</q-card-section>
            <q-card-section class="q-pt-none text-red">01/02/2019</q-card-section>
          </q-card>
        </q-list>
      </div>
    </q-drawer>

    <q-page-container>
       <q-card bordered class="q-ma-md">
          <q-card-section class="text-bold" style="text-align: center;font-size: 18px">
            Loan Closure Statistics
          </q-card-section>
          <q-card-section class="row justify-center">
            <div class="q-py-md">Amount</div><q-toggle v-model="toggle" label="Count" label-right />
          </q-card-section>
          <q-card-section class="row justify-center">
            <q-btn-group rounded>
              <q-btn color="amber" outline rounded label="YTD" />
              <q-btn color="amber" outline rounded label="MTD" />
              <q-btn color="amber" outline rounded label="WTD" />
            </q-btn-group>
          </q-card-section>
          <q-card-section>
            <bar-chart></bar-chart>
          </q-card-section>
       </q-card>

      <q-card bordered class="q-ma-md">
        <q-card-section class="text-bold" style="text-align: center;font-size: 18px">
          Confidence Meter (5)
        </q-card-section>
        <q-card-section>
          <d-chart></d-chart>
        </q-card-section>
      </q-card>

      <q-card bordered class="q-ma-md">
        <q-card-section class="text-bold" style="text-align: center;font-size: 18px">
          Pipeline Milestone (3)
        </q-card-section>
        <q-card-section class="row justify-center">
            <div class="q-py-md">Amount</div><q-toggle v-model="toggle" label="Count" label-right />
          </q-card-section>
        <q-card-section>
          <l-chart></l-chart>
        </q-card-section>
      </q-card>

    </q-page-container>

  </q-layout>
</template>

<script>
import BarChart from '../components/BarChart'
import DChart from '../components/DChart'
import LChart from '../components/LChart'

export default {
  data () {
    return {
      a: false,
      b: false,
      left: false,
      right: true,
      toggle: false
    }
  },
  components: {
    BarChart,
    DChart,
    LChart
  }
}
</script>

<style lang="stylus" scoped>

</style>
