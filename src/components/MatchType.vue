<template>
    <div>
        <div class="input-field col s12">
            <select id="example-1" v-model="selected" v-on:change="typeChosen">
                <option value="" disabled selected>Choose a match type</option>
                <option v-for="(type, index) in types" v-bind:value="index">
                {{type.message}} 
                </option>
            </select>
            <label>Type of match:</label>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Type',
    data: function(){
        return {
            types: [
                { message: 'Deathmatch' },
                { message: 'Domination' }
            ],
            selected: ''
        }
    },
    created: function(){
        $(document).ready(function() {
            $('select').material_select();
        });
    },
    methods: {
        typeChosen () {
            //We get the chosen match type
            var matchType = "hey";
            console.log("hola holita");
            //this.$parent.$emit('type', matchType);
        }
    }
}

function typeChosen (type) {
    console.log(type);
}
</script>

<style scoped>
	.blueTeamTitle{
		background-color: #03A694;
	}

</style>
