  
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
        class="mx-auto my-12"
        max-width="374"
      >
        <v-input >
            <v-text-field
            label="Username"
            class="my-4"
          ></v-text-field>
        </v-input>
        <v-input>
          <v-text-field
          label="Password"
          ></v-text-field>
        </v-input>
         <v-card-actions>
            <v-btn
              color="deep-purple lighten-2"
              text
              @click="reserve"
            >
              Login
            </v-btn>
               <v-btn
              color="deep-purple lighten-2"
              text
              @click="reserve"
            >
              Create
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
      drawer: null,
      items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'About', icon: 'mdi-help-box' },
        ],
      }),
  }
</script>