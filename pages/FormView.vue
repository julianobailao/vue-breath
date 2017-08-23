<template>
  <v-card class="elevation-0 section-def primary rounded-0 max-height-150">
    <v-card-title>
      <h1 class="title__main primary-text-color">Dashboard</h1>
      <h1 class="title__sub primary-text-color">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h1>
    </v-card-title>
    <v-card-text class="pt-0">
      <v-card class="section-def__card">
        <v-toolbar class="elevation-0">
          <v-btn
            icon
            to="/"
          >
            <v-icon>keyboard_backspace</v-icon>
          </v-btn>
          <v-breadcrumbs icons divider="chevron_right" class="pl-0 ml-1">
            <v-breadcrumbs-item>Teste</v-breadcrumbs-item>
            <v-toolbar-title>Titulo da sessao</v-toolbar-title>
          </v-breadcrumbs>
          <v-spacer></v-spacer>
          <v-btn
            class="secondary"
            dark
            small
            absolute
            bottom
            right
            fab
          >
            <v-icon>check</v-icon>
          </v-btn>
        </v-toolbar>
        <v-divider></v-divider>
        <v-card-text>
          <v-text-field
            name="input-1"
            label="Label Text"
            id="testing"
          ></v-text-field>
        </v-card-text>
      </v-card>
    </v-card-text>
  </v-card>
</template>
