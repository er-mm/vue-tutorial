<template>
    <div>
        <h2>This is a Popup</h2>
        <input type="text" v-model="popupName">
        <button @click="$emit('close', popupName)">Close popup</button>
    </div>
</template>

<script>
    export default {
        name: 'Popup',
        emits: {
            close: (popupName) => {
                if(!popupName) return false;
                else return true
            }
        },
        data() {
            return {
                popupName: ''
            }
        }
    }
</script>

<style scoped>

</style>