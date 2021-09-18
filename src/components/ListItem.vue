<template>
  <article class="justify-center items-center">
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.11.2/css/all.css"
    />
    <div
      class="
        xl:max-w-3xl
        xl:content-center
        bg-white
        p-3
        pb-1
        my-3
        rounded-xl
        shadow-lg
        transform
        hover:scale-105
        transition
        duration-500
      "
    >
      <!-- <h3 class="mb-3 text-xl font-bold text-indigo-600">Beginner Friendly</h3> -->
      <div class="relative">
        <g-image
          class="w-full rounded-xl"
          :src="item.imagens[0].src"
          alt="Colors"
        />
        <p
          class="
            absolute
            top-0
            bg-yellow-300
            text-gray-800
            font-semibold
            py-1
            px-3
            rounded-br-lg rounded-tl-lg
          "
        >
          R$ {{ item.preco }}
        </p>
      </div>
      <h1 class="mt-4 text-gray-800 text-3xl font-bold cursor-pointer">
        {{ item.title }}
        <ul class="flex">
          <li v-for="(n, index) in 4" :key="index">
            <i
              :class="[index < +item.nota[0] ? 'fa' : 'far']"
              class="fa-star fa-sm text-yellow-500 mr-1"
            ></i>
          </li>
        </ul>
      </h1>
      <div class="my-4">
        <div class="flex space-x-1 items-center">
          <span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 text-indigo-600 mb-1.5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
              />
            </svg>
          </span>
          <p>{{ item.cidade }}</p>
        </div>
        <div class="flex space-x-1 items-center">
          <span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 text-indigo-600 mb-1.5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
              />
            </svg>
          </span>
          <p>{{ item.date }}</p>
        </div>

        <div class="flex space-x-1 items-center"></div>
        <div></div>
        <g-link :to="item.path">
          <button
            class="
              mt-4
              text-xl
              font-bold
              w-full
              text-white
              bg-red-600
              py-2
              rounded-xl
              shadow-lg
            "
          >
            Ler comentários
          </button>
        </g-link>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  props: ["item"],
};
</script>