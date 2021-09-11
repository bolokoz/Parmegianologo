<template>
  <article class="justify-center items-center">
    <!-- Create By Joker Banny -->
    <!-- <div class="p-3 bg-gray-100 flex justify-center items-center">
      <div
        class="
          lg:max-w-lg
          container
          bg-white
          rounded-xl
          shadow-lg
          transform
          transition
          duration-500
          hover:scale-105
          hover:shadow-2xl
        "
      >
        <div>
          <h1
            class="
              text-2xl
              mt-2
              ml-4
              font-bold
              text-red-500
              cursor-pointer
              hover:text-gray-900
              transition
              duration-100
              uppercase
            "
          >
            {{ item.title }}
          </h1>
          <div class="flex space-x-2 mt-2 ml-3">
            <span>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-7 w-7 text-yellow-400"
                fill="none"
                viewBox="0 0 24 24"
                stroke="black"
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
            <h3 class="text-lg text-gray-600 font-semibold mb-2">
              {{ item.cidade }}
            </h3>
          </div>
        </div>
        <g-image
          class="w-full cursor-pointer"
          :src="item.preview_image"
          alt=""
        />
        <div class="flex p-4 justify-between">
          <div class="flex items-center space-x-2">
            <h2 class="text-gray-800 font-bold cursor-pointer">Nota</h2>
          </div>
          <div class="flex space-x-2">
            <div class="flex space-x-1 items-center">
              <span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-7 w-7 text-gray-600 cursor-pointer"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"
                  />
                </svg>
              </span>
            </div>
            <div class="flex space-x-1 items-center">
              <span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="
                    h-7
                    w-7
                    text-red-500
                    hover:text-red-400
                    transition
                    duration-100
                    cursor-pointer
                  "
                  viewBox="0 0 20 20"
                  fill="currentColor"
                >
                  <path
                    fill-rule="evenodd"
                    d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
                    clip-rule="evenodd"
                  />
                </svg>
              </span>
              <span>{{ item.date }}</span>
            </div>
          </div>
        </div>
      </div>
    </div> -->

    <div
      class="
        xl:max-w-3xl
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
          :src="item.preview_image"
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
                d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
              />
            </svg>
          </span>
          <p>{{ item.nota }}</p>
        </div>
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
      </div>
    </div>
  </article>
</template>

<script>
export default {
  props: ["item"],
};
</script>