<template>
    <div>
        <span>Type of match:</span>
	<div class="input-field col s12">
        	<select id="example-1">
	            <option value="" disabled selected>Choose a match type</option>
        	    <option v-for="(type, index) in types">
		            {{type.message}} 
	            </option>
		</select>
        	<label>Materialize Select hey</label>
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
    }
}
</script>
