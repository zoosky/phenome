<template>
  <f7-app :framework7="Framework7" :vue="Vue" :routes="routes">
    <f7-view :main="true" url="/" @swipeback:move="onSwipeBackMove"></f7-view>
  </f7-app>
</template>

<script>
  import Vue from 'vue';
  import Framework7 from 'framework7/dist/framework7.esm.bundle';

  import F7App from '../../../component-library/dist/vue/app';
  import F7View from '../../../component-library/dist/vue/view';

  import TestPage from './test-page.vue';
  import TestTab from './test-tab.vue';

  export default {
    components: {
      F7App,
      F7View,
    },
    methods: {
      onSwipeBackMove(e) {
        console.log(this, e);
      }
    },
    data() {
      return {
        Framework7,
        Vue,
        routes: [
          {
            path: '/',
            component: TestPage,
            tabs: [
              {
                id: 'tab1',
                path: '/',
                component: TestTab,
              },
              {
                id: 'tab2',
                path: 'tab2/',
                component: TestTab,
              },
              {
                id: 'tab3',
                path: 'tab3/',
                component: TestTab,
              },
            ]
          },
          {
            path: '/test2/',
            component: TestPage,
          },
          {
            path: '/test3/',
            component: TestPage,
          },
        ],
      };
    },
  };
</script>