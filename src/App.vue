<template>
  <div id="app">
      <Shapka />

    <router-view/>
  </div>
</template>

<script>
import Shapka from './components/layout/Header';
export default {
    name: "app",
    components: {
        Shapka
    }
}
</script>

<style>
    body {
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
        font-family: Georgia, 'Times New Roman', Times, serif;
    }
    .btn:hover {
        background: #666;
    }
</style>
