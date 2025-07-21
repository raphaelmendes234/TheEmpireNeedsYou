<template>
    <div class="corner top left"></div>
    <div class="corner top right"></div>
    <div class="corner bottom left"></div>
    <div class="corner bottom right"></div>
</template>

<style scoped>
    .corner{
        width: 2rem;
        height: 3px;
        position: absolute;
        background-color: var(--color-text);
    }
    .top{
        top: 0;
    }
    .bottom{
        bottom: 0;
    }
    .left{
        left: 0;
    }
    .right{
        right: 0;
    }
</style>