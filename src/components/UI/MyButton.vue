<script></script>
<template>
<button>
    <slot></slot> 
</button>
</template>
<style scoped>
button{
    border-radius: 10px;
    background: #FFF;
    box-shadow: 1px 5px 23px 0px rgba(35, 35, 35, 0.08);
    padding: 8px 20px;
    align-items: center;
    gap: 10px;
    display: flex;
    border: none;
    transition: all, 0.5s;
    cursor: pointer;
}
</style>