<template>
  <f7-page>
    <f7-navbar title="Searchbar">
      <f7-nav-right>
        <f7-link
          class="searchbar-enable"
          data-searchbar=".searchbar-demo"
          icon-ios="f7:search"
          icon-aurora="f7:search"
          icon-md="material:search"
        ></f7-link>
      </f7-nav-right>
      <f7-searchbar
        class="searchbar-demo"
        expandable
        search-container=".search-list"
        search-in=".item-title"
        :disable-button="!theme.aurora"
      ></f7-searchbar>
    </f7-navbar>
    <f7-list class="searchbar-not-found">
      <f7-list-item title="Nothing found"></f7-list-item>
    </f7-list>
    <f7-list class="search-list searchbar-found">
      <f7-list-item title="Volkswagen"></f7-list-item>
      <f7-list-item title="Volvo"></f7-list-item>
    </f7-list>
  </f7-page>
</template>
<script>
import { theme } from "framework7-vue";

export default {
  data() {
    return {
      theme,
    };
  },
};
</script>