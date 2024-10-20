<script setup lang="ts">
definePageMeta({
    middleware: "auth",
    auth: {
        guestRedirectUrl: "/sign-in",
    },
});
</script>

<template>
    <div>Page: pantry</div>
</template>

<style scoped></style>
