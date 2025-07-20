<template>
    <div class="card-container">
        <div class="heading">
            <slot name="icon"></slot>      
            <div>
                <h3 class="title"><slot name="title"></slot></h3>
                <p class="title-symbols"><slot name="title-symbols"></slot></p>
            </div>
        </div>
        <p><slot name="text"></slot></p>
    </div>
</template>

<style scoped>
.card-container{
    width: 100%;
    min-height: 192px;
    padding: 1rem;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    gap: 2rem;
    border: 1px solid var(--color-text);
}
.icon{
    width: 50px;
    height: 50px;
    background: red;
}
.heading{
    display: flex;
    justify-content: flex-start;
    align-items: center;
    gap: 1.5rem;
}
.title{
    text-transform: uppercase;
}
.title-symbols{
    color: var(--color-text);
}

@media (min-width: 1024px) {
   .card-container{
    padding: 3rem;
   } 
}
</style>