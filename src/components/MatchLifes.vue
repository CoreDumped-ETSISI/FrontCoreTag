<template>
    <div class="input-field col s6">
        <input id="lifes" type="text" v-on:keyup="setLifes">
        <label for="lifes">Lifes</label>
    </div>
</template>

<script>
export default {
    name: 'Lifes',
    methods: {
        setLifes(event){
            this.$parent.$emit('durationTime', event.target.value);
        }
    }

}

</script>
