<template>
    <div>
        <label>Duration:</label>
        <!-- Switch -->
        <div class="switch">
            <label>
                Infinite
                <input type="checkbox" v-on:click="durationSwitch">
                <span class="lever"></span>
                Finite
            </label>
        </div>
        <div v-if="switchState == 'Finite'">
            <br>
             <form action="#">
            <p>
            <input name="group1" type="radio" id="5" v-on:click="radioTime"/>
            <label for="5">5 mins</label>
            </p>
            <p>
            <input name="group1" type="radio" id="10" v-on:click="radioTime"/>
            <label for="10">10 mins</label>
            </p>
             </form>
        </div>

    </div>
</template>

<script>
export default {
    name: 'Duration',
    data: function(){
        return {
            switchState: 'Infinite'
        }
    },
    methods: {
        durationSwitch (event) {
            //We get the switch state
            var state = event.target.checked;
            if(state == true){
                //Set the DOM variable data
                this.switchState = 'Finite';
                this.$parent.$emit('duration', 'finite');
            }else{
                //Set the DOM variable data
                this.switchState = 'Infinite';
                this.$parent.$emit('duration', 'infinite');
            }
        },
        radioTime (event) {
            console.log(event.target.id);
            this.$parent.$emit('durationTime', event.target.id);
        }
    }
}
</script>
