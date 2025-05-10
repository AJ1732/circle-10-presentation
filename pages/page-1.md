# Circle 10

Presentation slides

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>
  
<div class="abs-br w-full m-6 text-xl">
  <script setup>
    const teamMembers =
     ["Osezele Ejemen Iboi", "Ibraheem Abdulrahman", "Akangbe, Ooreoluwa Patience", "Abdullahi Abdulkadir", "Ezeagu Chiamaka Vanessa", "Okolo Deborah"]
  </script>

  <ul class="flex flex-wrap justify-center items-center gap-4">
      <li v-for="item in teamMembers" :key="item">
      {{ item }}
    </li>
  </ul>
</div>

<style>
  ul {
    list-style: none;

    li {
      font-size: 0.875rem;
      color: #262626;
    }
  }
</style>
