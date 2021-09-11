<template>
  <footer
    class="block w-full md:flex md:justify-between px-5 pt-10 bg-red-700 mt-10"
  >
    <div class="footer-section md:self-start">&copy; Parmegianólogo</div>
    <div class="footer-section">parmegianologo.netlify.app</div>
    <div class="footer-section social">
      <g-link href="https://instagram.com/parmegianologo">
        <font-awesome :icon="['fab', 'instagram']" size="2x" />
      </g-link>
      <g-link href="https://github.com/bolokoz/parmegianologo">
        <font-awesome :icon="['fab', 'github']" size="2x" />
      </g-link>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style>
.footer-section {
  @apply block text-center text-xs py-2 text-white mx-auto;
}

.social a {
  @apply p-1;
}
</style>