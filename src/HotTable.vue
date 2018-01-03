<template>
  <no-ssr placeholder="Loading...">
    <div :id="this.root"></div>
  </no-ssr>
</template>

<script>
  import Handsontable from 'handsontable';
  import SettingsMapper from './settingsMapper';
  import {
    hotInit,
    hotDestroy,
    propFactory,
    propWatchFactory,
    updateHotSettings,
    updateBulkHotSettings
  } from './helpers';
  export default {
    name: 'HotTable',
    props: propFactory(),
    watch: propWatchFactory(updateHotSettings, updateBulkHotSettings),
    mounted: function() { return hotInit(this); },
    beforeDestroy: function() { return hotDestroy(this); },
  };
</script>

<style>
  @import "handsontable/dist/handsontable.full.css";
</style>
