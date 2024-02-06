<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)
const menus = [
    {
        id: 1,
        name: "Home",
        path: "#home"
    },
    {
        id: 2,
        name: "Profile",
        path: "#profile"
    },
    {
        id: 3,
        name: "Projects",
        path: "#project"
    },
    {
        id: 4,
        name: "Contact",
        path: "#contact"
    },
]
</script>

<template>
  <header class="bg-slate-800 bg-opacity-90 shadow-2xl min-w-full fixed">
    <nav
      class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8"
      aria-label="Global"
    >
      <div class="flex lg:flex-1">
        <a href="#" class="-m-1.5 p-1.5">
          <span class="font-black text-2xl/loose tracking-wider">R D O</span>
        </a>
      </div>
      <div class="flex lg:hidden md:hidden">
        <SideMenu :menus="menus" />
      </div>
      <div class="hidden lg:flex md:flex gap-10">
        <ul v-for="menu in menus" :key="menu.id">
            <li>
                <RouterLink :to="menu.path" class="hover:text-lime-600">{{menu.name}}</RouterLink>
            </li>
        </ul>
      </div>
    </nav>
  </header>
</template>
