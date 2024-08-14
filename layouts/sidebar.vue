<template>
    <main class="user-layout">
        <article class="sidebar">
            <p >Settings</p>
            <p>Dashboard</p>
        </article> // 
        <section>
            <slot></slot>

        </section>
    </main>
</template>

<style scoped>
.sidebar {
    display: flex;
    flex-direction: column;
}
.user-layout{
    display: flex;
}
</style>