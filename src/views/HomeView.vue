<script setup>
  import { ref } from "vue";
  import RecipeCard from "@/components/RecipeCard.vue";
  import Button from "@/components/Button.vue";
  import NavButton from "@/components/NavButton.vue";
  let open = ref(false);
</script>
<template>
  <div class="grid md:grid-cols-3">
    <div class="md:col-span-1">
      <nav class="text-right">
        <div class="flex md:block justify-between items-center">
          <h1 class="uppercase font-bold p-4 border-b border-gray-100">
            <a href="/" class="hover:text-gray-700">Food Ninja</a>
          </h1>
          <div class="cursor-pointer px-4" @click="open = !open">
            <span class="material-symbols-rounded w-6 md:hidden"> menu </span>
          </div>
        </div>
        <ul
          class="mt-6 md:flex flex-col gap-2"
          :class="{ hidden: open === false, 'md:flex': open === true }"
        >
          <NavButton :active="true" name="Home" icon="home"></NavButton>
          <NavButton :active="false" name="About" icon="help"></NavButton>
          <NavButton :active="false" name="Contact" icon="mail"></NavButton>
        </ul>
      </nav>
    </div>

    <main class="px-16 py-6 bg-gray-100 md:col-span-2">
      <div class="flex justify-center md:justify-end gap-4">
        <Button><template #default>Log In</template></Button>
        <Button><template #default>Sign Up</template></Button>
      </div>

      <header>
        <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
        <h3 class="text-2xl font-semibold">For Ninjas</h3>
      </header>

      <div>
        <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">
          Latest Recipes
        </h4>

        <div class="mt-8 grid lg:grid-cols-3 gap-10">
          <!-- cards go here -->
          <RecipeCard name="5 Bean Chilli Stew" image="stew"></RecipeCard>
          <RecipeCard name="Veg Noodles" image="noodles"></RecipeCard>
          <RecipeCard name="Tofu Curry" image="curry"></RecipeCard>
        </div>

        <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">
          Most Popular
        </h4>

        <div class="mt-8 grid lg:grid-cols-3 gap-10">
          <!-- cards go here -->
          <RecipeCard name="5 Bean Chilli Stew" image="stew"></RecipeCard>
          <RecipeCard name="Veg Noodles" image="noodles"></RecipeCard>
          <RecipeCard name="Tofu Curry" image="curry"></RecipeCard>
        </div>
      </div>

      <div class="flex justify-center mt-10">
        <div
          class="bg-secondary-100 text-secondary-200 btn hover:shadow-inner transform hover:scale-110 hover:bg-opacity-50 transition ease-out duration-200"
        >
          Load more
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped></style>
