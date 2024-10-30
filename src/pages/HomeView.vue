<template>
  <div class="">
    <v-parallax
      src="https://images.unsplash.com/photo-1610241436112-b76fa54258c5?q=80&w=2072&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
      height="500">
      <div class="d-flex flex-column fill-height justify-center align-center text-white">
        <h1 class="text-h4 font-weight-thin mb-4 ">
          Nimit Trevadiya
        </h1>
        <h4 class="subheading">
          Welcomes with the cool setup!
        </h4>
      </div>
    </v-parallax>
    <v-container-fluid>
      <div class="my-5">
        <div class="my-5">

          <v-row>
            <v-col>
              <v-btn prepend-icon="$vuetify" variant="tonal" @click="showAlert('success')" class="text-indigo">
                show alert
              </v-btn>
            </v-col>
            <v-col>
              <v-btn prepend-icon="$vuetify" variant="tonal" @click="showAlert('error')" block class="text-indigo">
                show alert
              </v-btn>
            </v-col>
          </v-row>
        </div>
        <v-expansion-panels>
          <v-expansion-panel title="Title"
            text="Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi, ratione debitis quis est labore voluptatibus! Eaque cupiditate minima">
          </v-expansion-panel>
        </v-expansion-panels>
      </div>
      <v-container-fluid>
        <Tab />
      </v-container-fluid>
    </v-container-fluid>

    <v-parallax
      src="https://images.unsplash.com/photo-1610241436112-b76fa54258c5?q=80&w=2072&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D">
      <div class="d-flex flex-column fill-height justify-center align-left text-white ml-5">
        <h1 class="text-h4 font-weight-thin mb-4">
          Welcomes with the cool setup!
        </h1>
        <h4 class="subheading text-wrap " style="max-width: 336px;">
          This is just starting of the coolest components now wait and scroll
        </h4>
      </div>
    </v-parallax>
  </div>
</template>

<script lang="ts" setup>
//
import { AlertInterface } from '@/Interfaces/store';
import { useStore } from 'vuex';

import Tab from '@/components/globle/tabs/TabsComponent.vue';
const store = useStore();

const showAlert = (type: "error" | "warning" | "success" | "info") => {
  store.dispatch('updateAlertDetails', {
    showAlert: true,
    title: 'This is an alert title',
    text: 'This is an alert text',
    icon: 'mdi-alert',
    variant: 'tonal',
    closable: true,
    type: type
  } as AlertInterface);
};
</script>
