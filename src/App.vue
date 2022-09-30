<template>
  <nav>
    <!--Menu petits écran-->
    <div class=" lg:hidden flex items-center">
      <button v-on:click="menuNav = !menuNav " class=" py-6 px-3 ">
        <Bars3Icon class="h-10 w-10 text-indigo-700" :class="{hidden: !menuNav}" />
      </button>
    </div>

    <div class="flex flex-row-reverse" :class="{hidden: menuNav }">
      <button v-if="!menuNav" v-on:click="menuNav = !menuNav" class=" py-6 px-3 ">
        <XMarkIcon class="h-10 w-10 text-indigo-600" />
      </button>
      <ul>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/">
            lien vers
            <code class="font-mono">/src/pages/index.vue</code>
          </router-link>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/simple">
            <h2>lien vers Page Simple</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste">
            <h2>lien vers Page Liste</h2>
          </router-link>
        </li>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste-fetch">
            <h2>lien vers Page Liste-fetch</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/edit/new">
            <h2>lien vers Page New</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste-supabase">
            <h2>lien vers Page Liste-supabase</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/login-logout">
            <h2>Se connecter / Créer un compte</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/edit/id">
            <h2>Page ID</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/quartier">
            <h2>Index quartier</h2>
          </router-link>
        </li>
      </ul>
    </div>

    <!--Menu grands écrans-->

    <div class="hidden lg:flex justify-center bg-indigo-100">
      <ul>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/">
            lien vers
            <code class="font-mono">/src/pages/index.vue</code>
          </router-link>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/simple">
            <h2>lien vers Page Simple</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste">
            <h2>lien vers Page Liste</h2>
          </router-link>
        </li>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste-fetch">
            <h2>lien vers Page Liste-fetch</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/edit/new">
            <h2>lien vers Page New</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/liste-supabase">
            <h2>lien vers Page Liste-supabase</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/login-logout">
            <h2>Se connecter / Créer un compte</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-red-600 underline font-bold" to="/edit/id">
            <h2>Page ID</h2>
          </router-link>
        </li>
      </ul>
    </div>


  </nav>
  <!-- Affiche les pages -->
  <Suspense>
    <router-view class="m-2 border-2 p-2" />
  </Suspense>
</template>

<script setup lang="ts">
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/20/solid';
import { ref } from 'vue';
const menuNav = ref(true);
</script>
