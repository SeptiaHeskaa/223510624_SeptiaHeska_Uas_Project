<template>
  <q-layout view="lHh lpr lFf">
    <q-header elevated class="custom-header">
      <q-toolbar>
        <q-btn flat round dense icon="assignment_ind" class="custom-icon" />
        <q-space />
        <q-toolbar-title class="custom-title">WEATHER</q-toolbar-title>
        <q-space />
        <q-btn-dropdown flat class="custom-btn" label="PROJECT PBK">
          <q-list>
            <q-item clickable @click="navigateToLink('https://t1septiaheska.netlify.app/')">
              <q-item-section>
                TUGAS 1
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://septiaheskatugas2.netlify.app/')">
              <q-item-section>
                TUGAS 2
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://6644cecae35ed52df42962f1--septiaheskat3.netlify.app/')">
              <q-item-section>
                TUGAS 3
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://223510624-septi.netlify.app/')">
              <q-item-section>
                TUGAS 4
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://223510624-septia-t5.netlify.app/')">
              <q-item-section>
                TUGAS 5
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://septiiiiiaaaaa.netlify.app/')">
              <q-item-section>
                TUGAS 6
              </q-item-section>
            </q-item>
            <q-item clickable @click="navigateToLink('https://septiaheskaaaaa.netlify.app/')">
              <q-item-section>
                TUGAS 7
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
        <q-space style="margin-right: 8px;" />
        <q-btn flat round dense icon="sim_card" class="custom-icon" />
        <q-btn flat round dense icon="gamepad" class="custom-icon" />
      </q-toolbar>
    </q-header>

    <q-page-container class="custom-page-container">
      <q-page class="custom-page">
        <!-- Include Weather component and pass the apiKey prop -->
        <Weather :apiKey="apiKey" />
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue';
import Weather from './views/Weather.vue'; 

export default {
  name: 'App',
  components: {
    Weather,
  },
  data() {
    return {
      apiKey: '68c1a0b3f0bad0da39e6296c1197a9f2', 
    };
  },
  methods: {
    navigateToLink(url) {
      window.open(url, '_blank');
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');

body {
  font-family: 'Roboto', sans-serif;
  background-color: #8c00ff;
  margin: 0;
  padding: 0;
  height: 100vh; /* Ensures the body takes the full viewport height */
}

.custom-layout {
  background: linear-gradient(135deg, #ece9e6, #ffffff);
  height: 100vh; /* Ensures the layout takes the full viewport height */
}

.custom-header {
  background: linear-gradient(135deg, #3c4566, #8000ff) !important;
  border-bottom: 2px solid #000103;
}

.custom-title {
  font-family: 'Roboto', sans-serif;
  font-size: 2rem; /* Increased font size */
  font-weight: 800; /* Increased font weight */
  color: #ffffff;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3); /* Added text shadow */
}

.custom-btn .q-btn__content {
  color: #ffffff;
  font-weight: 500;
}

.custom-select .q-field__control {
  border-radius: 8px;
  border: 2px solid #f5a623;
  background-color: #ffffff;
  color: #3a3f51;
}

.custom-select .q-field__control:hover {
  border-color: #ffce00;
}

.custom-icon {
  color: #ffffff !important;
  transition: background-color 0.3s, color 0.3s;
}

.custom-icon:hover {
  background-color: #f5a623 !important;
  color: #ffffff !important;
}

.custom-page-container {
  background-color: #8400ff98;
  display: flex;
  flex: 1; /* Allows the container to take up remaining height */
  justify-content: center;
  align-items: center;
  height: 100%; /* Takes up the full height of the layout */
}

.custom-page {
  position: relative;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  padding: 20px;
  transition: box-shadow 0.3s;
  max-width: 600px;
  width: 100%;
  background-image: url('.\assets\bgWeatther.jpg');
  background-size: 95%; /* Ensures the image covers the container */
  background-position: center; /* Centers the image in the container */
  overflow: hidden; /* Ensures the overlay doesn't exceed the container bounds */
}

.custom-page::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: hsla(198, 34%, 79%, 0.22); /* Adjust the opacity as needed */
  z-index: 1; /* Places the overlay on top of the background image */
}

.custom-page > * {
  position: relative;
  z-index: 2; /* Ensures the content is above the overlay */
}

.custom-page:hover {
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.q-btn {
  color: #ffffff;
  border-radius: 50%;
}

.q-btn:hover {
  background-color: #c1beb8;
  color: #ffffff;
}

.shadow-2 {
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.rounded-borders {
  border-radius: 12px;
}

</style>
