<template>
<nav>
  <div>
    <span>Type of match:</span>
	<div class="input-field col s12">
		<select>
		    <option value="" disabled selected>Choose a match type</option>
	            <option v-for="(type, index) in types" value={{index}}>
		   	{{type}} 
		    </option>
		</select>
		<label>Materialize Select</label>
	</div>
  </div>
</nav>
</template>

<script>
	export default {
		name: 'Type',
		data: {
			return:{
				types: [ message: 'FREE-4-ALL' ]
			}
		}
	}
</script>
