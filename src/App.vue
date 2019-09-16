<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

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
