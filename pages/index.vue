<script setup>
import { ref } from "vue";
definePageMeta({
    middleware: "auth",
    auth: {
        guestRedirectUrl: "/sign-in",
    },
});

const meals = ref([
    {
        title: "Spaghetti Bolognese",
        description: "A delicious Italian pasta dish...",
        link: "/recipe/1",
    },
    {
        title: "Chicken Caesar Salad",
        description: "A refreshing salad with crispy...",
        link: "/recipe/2",
    },
    {
        title: "Beef Tacos",
        description: "Mexican-style tacos with spicy beef...",
        link: "/recipe/3",
    },
    {
        title: "Spaghetti Bolognese",
        description: "A delicious Italian pasta dish...",
        link: "/recipe/4",
    },
    {
        title: "Chicken Caesar Salad",
        description: "A refreshing salad with crispy...",
        link: "/recipe/5",
    },
    {
        title: "Beef Tacos",
        description: "Mexican-style tacos with spicy beef...",
        link: "/recipe/6",
    },
    {
        title: "Beef Tacos",
        description: "Mexican-style tacos with spicy beef...",
        link: "/recipe/7",
    },
    // Add more meals for each day of the week...
]);

function truncateDescription(description) {
    return description.length > 60
        ? description.slice(0, 60) + "..."
        : description;
}
</script>

<template>
    <div class="p-6">
        <h1 class="text-3xl font-bold mb-6">Your Weekly Meals</h1>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <div
                v-for="(meal, index) in meals"
                :key="index"
                class="card shadow-lg bg-base-100"
            >
                <div class="card-body p-4">
                    <h2 class="text-xl font-bold mb-4">
                        {{ meal.day ?? "Monday" }}
                    </h2>
                    <figure>
                        <img
                            :src="meal.image"
                            :alt="meal.title"
                            class="rounded-lg object-cover h-40 w-full"
                        />
                    </figure>
                    <h3 class="text-lg font-semibold mt-4">
                        {{ meal.title }}
                    </h3>
                    <p class="text-sm mt-2">
                        {{ truncateDescription(meal.description) }}
                    </p>
                    <div class="card-actions justify-center mt-4">
                        <NuxtLink :to="meal.link" class="btn btn-primary w-full"
                            >View Recipe</NuxtLink
                        >
                        <NuxtLink :to="meal.link" class="btn btn-primary w-full"
                            >View Recipe</NuxtLink
                        >
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
