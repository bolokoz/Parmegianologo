<template>
  <div class="container mx-auto w-3/4 py-3">
    <div class="bg-red mb-3 pb-4" v-for="item in articles" :key="item.node.id">
      <g-link :to="item.node.path" class="article-link">
        <g-image
          :src="item.node.preview_image"
          :alt="item.node.title"
          class="rounded-t-lg object-cover object-center h-64"
          v-if="item.node.preview_image"
        />
        <p class="text-xl font-bold pt-3">{{ item.node.title }}</p>
        <p class="text-sm font-light py-2">{{ item.node.date }}</p>
        <div class="">
          <span
            class="
              text-xs text-gray-700
              bg-gray-200
              font-semibold
              p-2
              my-2
              mx-1
            "
            v-for="(item, index) in +item.node.nota[0]"
            :key="index"
          >
            {{ item }}
            <svg
              class="block h-5 w-5"
              fill="blue"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
            >
              <path
                d="M10 15l-5.878 3.09 1.123-6.545L.489 6.91l6.572-.955L10 0l2.939 5.955 6.572.955-4.756 4.635 1.123 6.545z"
              /></svg
          ></span>
        </div>
      </g-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    articles: {
      type: Array,
      required: true,
    },
  },
};
</script>