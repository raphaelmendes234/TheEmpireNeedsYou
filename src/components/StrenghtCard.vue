<template>
    <div class="card-container">
        <div class="heading">
            <slot name="icon"></slot>      
            <div>
                <h3 class="title"><slot name="title"></slot></h3>
                <p class="symbols"><slot name="symbols"></slot></p>
            </div>
        </div>
        <p><slot name="text"></slot></p>
    </div>
</template>

<style scoped>
.card-container{
    width: 100%;
    height: 100%;
    min-height: 192px;
    padding: 1rem;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    border: 1px solid var(--color-text);
}
.heading{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 1rem;
}
.title{
    text-transform: uppercase;
}

@media (min-width: 768px) {
    .card-container{
        padding: 2rem;
        gap: 1.5;
    } 
    .heading{
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        gap: 1.5rem;
    }
}

@media (min-width: 1024px) {
    .card-container{
        padding: 3rem;
        gap: 2rem;
    } 
}
</style>