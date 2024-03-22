<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <h2>{{ header }}</h2>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['header', 'text', 'theme'],
        methods: {
            closeModal(){
                this.$emit('close')
            }
        }
    }
    
</script>


<style scoped>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background-color: #cdc;
        width:100%;
        height: 100%;
    }
    .modal p{
        font-size: 12px;
        font-weight: 900;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
</style>