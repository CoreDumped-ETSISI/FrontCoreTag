<<template>
    <div class="teamMatchup">
      <h1>Players, match up to next battle!</h1>
      <p>Set your nickname into the browser, and pick a team! 
        If you prefer to randomize the match up, just hit the random button!</p>

      <div class="row">
        <div class="input-field col s12">
          <i class="material-icons prefix"></i>
          <input type="text" id="autocomplete-input" class="autocomplete">
          <label for="autocomplete-input">Type your nickname!</label>
        </div>
      </div>
    
    </div>

</template>

<script>
export default {
  name:'Players',
  created: function (){
    
    $('input.autocomplete').autocomplete({
    data: {
      "Apple": null,
      "Microsoft": null,
      "Google": 'https://placehold.it/250x250'
    },
    limit: 20, // The max amount of results that can be shown at once. Default: Infinity.
    onAutocomplete: function(val) {
      // Callback function when value is autcompleted.
    },
    minLength: 1, // The minimum length of the input for the autocomplete to start. Default: 1.
  });
  }
  
}
</script>
