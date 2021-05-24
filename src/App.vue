  
<template>
  <v-app id="inspire">
    <v-navigation-drawer 
      v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
        <v-card
    class="mx-auto"
    max-width="400"
  >
    <v-list-item two-line>
      <v-list-item-content>
        <v-list-item-title class="headline">
          San Francisco
        </v-list-item-title>
        <v-list-item-subtitle>Mon, 12:30 PM, Mostly sunny</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-card-text>
      <v-row align="center">
        <v-col
          class="display-3"
          cols="6"
        >
          23&deg;C
        </v-col>
        <v-col cols="6">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sun.png"
            alt="Sunny image"
            width="92"
          ></v-img>
        </v-col>
      </v-row>
    </v-card-text>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-send</v-icon>
      </v-list-item-icon>
      <v-list-item-subtitle>23 km/h</v-list-item-subtitle>
    </v-list-item>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-cloud-download</v-icon>
      </v-list-item-icon>
      <v-list-item-subtitle>48%</v-list-item-subtitle>
    </v-list-item>

    <v-slider
      v-model="time"
      :max="6"
      :tick-labels="labels"
      class="mx-4"
      ticks
    ></v-slider>

    <v-list class="transparent">
      <v-list-item
        v-for="item in forecast"
        :key="item.day"
      >
        <v-list-item-title>{{ item.day }}</v-list-item-title>

        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-subtitle class="text-right">
          {{ item.temp }}
        </v-list-item-subtitle>
      </v-list-item>
    </v-list>

    <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip>5:30PM</v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
    </v-card-text>

    <v-divider></v-divider>

    <v-card-actions>
      <v-btn text>
        Full Report
      </v-btn>
    </v-card-actions>
  </v-card>

    <!---
    <v-card>
			<v-card-content>
				<v-input-container class="v-block">
					<label>Username</label>
					<input ng-model="home.username" ng-required="true">
				</v-input-container>
				<v-input-container class="v-block">
					<label>Password</label>
					<input ng-model="home.password" type="password" ng-required="true">
				</v-input-container>
				<ng-messages for="home.error" role="alert" class="v-block">
					<ng-message when="error">{{home.error.error}}</ng-message>
				</ng-messages>
			</v-card-content>
			<v-card-actions layout="row" layout-align="end center">
				<v-button type="submit" class="v-primary">Login</v-button>
				<v-button type="submit">Create</v-button>
			</v-card-actions>
		</v-card> -->
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
     labels: ['SU', 'MO', 'TU', 'WED', 'TH', 'FR', 'SA'],
        time: 0,
        forecast: [
          { day: 'Tuesday', icon: 'mdi-white-balance-sunny', temp: '24\xB0/12\xB0' },
          { day: 'Wednesday', icon: 'mdi-white-balance-sunny', temp: '22\xB0/14\xB0' },
          { day: 'Thursday', icon: 'mdi-cloud', temp: '25\xB0/15\xB0' },
        ],
      drawer: null,
      items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'About', icon: 'mdi-help-box' },
        ],
      }),
  }
</script>