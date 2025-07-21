<template>
    <div class="card-container">
        <div class="heading">
            <p class="number"><slot name="number"></slot> </p>     
            <div class="title-wrapper">
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
    padding: 2rem 1rem;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
.heading{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 1rem;
}
.number{
    font-family: 'Distant Galaxy Outline';
    font-weight: normal;
    font-size: 3rem;
}
.title-wrapper{
    width: 100%;
}
.title{
    text-align: left;
    text-transform: uppercase;
}

@media (min-width: 768px) {
    .card-container{
        width: 65%;
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
    .number{
        font-size: 5rem;
    }
}

@media (min-width: 1280px) {
    .card-container{
        width: 50%;
    } 
}
</style>