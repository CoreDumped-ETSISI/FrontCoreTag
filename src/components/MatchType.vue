<template>
    <div>
	<div class="input-field col s12">
        	<select id="example-1" v-on:change="typeChosen">
	            <option value="" disabled selected>Choose a match type</option>
        	    <option v-for="(type, index) in types">
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
            ]
        }
    },
    created: function(){
            $(document).ready(function() {
                $('select').material_select();
            });
    },
    methods: {
        typeChosen (event) {
        	//We get the chosen match type
        	var matchType = "hey";
		console.log("hola holita");
        	//this.$parent.$emit('type', matchType);
        }
    }
}
</script>

<style scoped>
	.blueTeamTitle{
		background-color: #03A694;
	}

</style>
