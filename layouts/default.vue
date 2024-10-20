<script setup lang="ts"></script>

<template>
    <div class="h-screen flex">
        <div class="drawer lg:drawer-open">
            <input id="my-drawer-2" type="checkbox" class="drawer-toggle" />
            <div class="drawer-content flex flex-col overflow-y-scroll">
                <div class="flex items-center">
                    <label
                        for="my-drawer-2"
                        class="btn btn-ghost drawer-button lg:hidden place-self-start"
                    >
                        <Icon
                            name="heroicons:arrow-right-start-on-rectangle-20-solid"
                            size="1.4em"
                        />
                    </label>
                    <NuxtLink to="/" class="lg:hidden">
                        <span class="text-2xl font-bold">Remmi</span>
                    </NuxtLink>
                </div>
                <slot />
            </div>
            <div class="drawer-side">
                <label
                    for="my-drawer-2"
                    aria-label="close sidebar"
                    class="drawer-overlay"
                ></label>
                <ul
                    class="menu bg-base-200 text-base-content min-h-full w-80 p-4"
                >
                    <aside class="w-64 bg-base-200 p-4">
                        <NuxtLink
                            to="/"
                            class="btn btn-ghost flex items-center justify-center"
                        >
                            <h2 class="text-2xl font-bold">Remmi</h2>
                        </NuxtLink>
                    </aside>
                    <ul
                        class="menu bg-base-200 text-base-content min-h-full w-full p-4"
                    >
                        <li>
                            <NuxtLink to="/recipe-generator"
                                >Recipe Generator</NuxtLink
                            >
                        </li>
                        <li>
                            <NuxtLink to="/recipe-book">Recipe Book</NuxtLink>
                        </li>
                        <li><NuxtLink to="/pantry">Pantry</NuxtLink></li>
                    </ul>
                </ul>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Add any custom styles if needed */
</style>
