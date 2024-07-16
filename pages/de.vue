<template>
    <v-sheet color="#0d1117" elevation="3" rounded="lg">
      <v-tabs
        v-model="tab"
        :items="tabs"
        align-tabs="center"
        color="white"
        height="60"
        slider-color="#f78166"
      >
        <template v-slot:tab="{ item }">
          <v-tab
            :prepend-icon="item.icon"
            :text="item.text"
            :value="item.value"
            class="text-none"
          ></v-tab>
        </template>
  
        <template v-slot:item="{ item }">
          <v-tabs-window-item :value="item.value" class="pa-4">
            <div v-if="item.value === 'tab-1'">
              <h3>Readme</h3>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi, ratione debitis quis est labore voluptatibus!</p>
            </div>
            <div v-else-if="item.value === 'tab-2'">
              <h3>Code of Conduct</h3>
              <p>Eaque cupiditate minima, at placeat totam, magni doloremque veniam neque porro libero rerum unde voluptatem!</p>
            </div>
            <div v-else-if="item.value === 'tab-3'">
              <h3>MIT License</h3>
              <p>This software is licensed under the MIT License. For more information, visit the official website.</p>
            </div>
            <div v-else-if="item.value === 'tab-4'">
              <h3>Security</h3>
              <p>Security is our top priority. Please report any vulnerabilities to our security team.</p>
            </div>
          </v-tabs-window-item>
        </template>
      </v-tabs>
    </v-sheet>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tab: 'tab-1',
        tabs: [
          {
            icon: 'mdi-book-open-page-variant',
            text: 'Readme',
            value: 'tab-1',
          },
          {
            icon: 'mdi-handshake-outline',
            text: 'Code of Conduct',
            value: 'tab-2',
          },
          {
            icon: 'mdi-license',
            text: 'MIT License',
            value: 'tab-3',
          },
          {
            icon: 'mdi-shield-lock-outline',
            text: 'Security',
            value: 'tab-4',
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .text-none {
    text-transform: none;
  }
  </style>
  