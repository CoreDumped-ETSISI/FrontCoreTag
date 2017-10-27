<template>
    <div>
    <label>Duration:</label>
      <!-- Switch -->
  <div class="switch">
    <label>
      Off
      <input type="checkbox" v-on:click="durationSwitch">
      <span class="lever"></span>
      On
    </label>
  </div>
  </div>
</template>

<script>
export default {
    name: 'Duration',
    methods: {
        durationSwitch (event) {
            if(event == true){
                console.log("True");
            }else{
                console.log('false');
            }
        },
    }
}
</script>
