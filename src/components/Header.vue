<template>
  <div id="nav" class="flex fixed w-full justify-around bg-blue-400 p-4 capitalize text-white text-xl">
    <router-link to="/" class="font-bold">Home</router-link>
    <router-link to="/cart">Cart</router-link>
  </div>
</template>

<style>
  #nav a.router-link-exact-active{
    color: springgreen;
    transform: scale(1.2);
  }
</style>