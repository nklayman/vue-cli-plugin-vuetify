<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
        <%_ if (options.iconFont === 'mdi') { _%>
        <v-icon>mdi-open-in-new</v-icon>
        <%_ } else if (options.iconFont === 'md') { _%>
        <v-icon>open_in_new</v-icon>
        <%_ } else if (options.iconFont === 'fa') { _%>
        <v-icon>fas fa-external-link-alt</v-icon>
        <%_ } else if (options.iconFont === 'fa4') { _%>
        <v-icon>fa-external-link</v-icon>
        <%_ } _%>
      </v-btn>
    </v-app-bar>

    <v-content>
      <%_ if (options.router) { _%>
      <router-view/>
      <%_ } else { _%>
      <HelloWorld/>
      <%_ } _%>
    </v-content>
  </v-app>
</template>

<script>
<%_ if (!options.router) { _%>
import HelloWorld from './components/HelloWorld';
<%_ } _%>

export default {
  name: 'App',
  <%_ if (!options.router) { _%>
  components: {
    HelloWorld,
  },
  <%_ } _%>
  data: () => ({
    //
  }),
};
</script>
