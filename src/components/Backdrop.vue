<template>
    <div class="backdrop" >
        <slot></slot>
    </div>
</template>

<style scoped>
.backdrop{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.623);
    z-index: 999;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>