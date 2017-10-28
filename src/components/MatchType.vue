<template>
	<div>
		<span>Type of match:</span>
		<ul>
			<li>primero</li>
			<li>segundo</li>
			<li>tercero</li>
			<li>cuarto</li>
			<li v-for="item in items">{{ item.message }}</li>
		</ul>
<!--		<div class="input-field col s12">
			<select id="example-1">
			    <option value="" disabled selected>Choose a match type</option>
		            <option v-for="(type, index) in types">
			   	{{type.message}} 
			    </option>
			</select>
			<label>Materialize Select hey</label>
		</div>
-->	</div>
</template>

<script>
	export default {
		name: 'Type',
		data: {
			items: [
				{ message: 'Foo' },
				{ message: 'Bar' }
			]
		},
/*		created: function(){
			$(document).ready(function() {
				$('select').material_select();
			});
		}*/
	}
</script>
