<template>
  <header>
    <nav class="flex justify-between flex-wrap">
      <div class="flex flex-shrink-0 text-white items-end ml-5">
        <g-link :to="{ name: 'home' }" class="visible font-semibold text-xl">
          <g-image
            src="~/favicon.png"
            class="h-10 object-center object-fit w-10 inline-block"
          />
          <span class="text-green-700 align-bottom leading-snug ml-5"
            >Parmegianólogo</span
          >
        </g-link>
      </div>
      <div class="visible md:hidden mr-5">
        <button
          @click="toggleCollapsed()"
          class="
            flex
            px-3
            py-2
            border
            rounded
            text-green-700
            border-green-700
            hover:text-green-900
            hover:border-black
          "
        >
          <svg
            class="fill-current h-3 w-3"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div class="w-full block lg:flex lg:items-center lg:w-auto font-semibold">
        <div class="text-md lg:flex-grow mt-6" v-if="collapsed">
          <g-link to="/" class="nav-link md:inline-flex md:text-left"
            >Parmegianas</g-link
          >
          <g-link to="/tabela" class="nav-link md:inline-flex md:text-left"
            >Tabela</g-link
          >
          <g-link to="/sobre" class="nav-link md:inline-flex md:text-left"
            >Sobre</g-link
          >
          <a
            href="https://parmegianologo.netlify.app/admin"
            class="nav-link md:inline-flex md:text-left"
            >Admin
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      collapsed: true,
    };
  },
  methods: {
    toggleCollapsed() {
      this.collapsed = !this.collapsed;
    },
  },
};
</script>

<style>
.nav-link {
  @apply block text-center text-green-700 mr-4 align-bottom leading-snug;
}

.nav-link:hover {
  @apply text-green-900 underline font-bold;
}
</style>