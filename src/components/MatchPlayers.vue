<<template>
    <div class="teamMatchup">
      <h1>Players, match up to next battle!</h1>
      <p>Set your nickname into the browser, and pick a team! 
        If you prefer to randomize the match up, just hit the random button!</p>

      <div class="row">
        <div class="col s12">
          <div class="row">
            <div class="input-field col s12">
              <input type="text" id="autocomplete-input" class="autocomplete">
              <label for="autocomplete-input">Type your nickname!</label>
            </div>
          </div>
        </div>
      </div>

    </div>

</template>

<script>
export default {
  name:'Players',
  created: function () {
    $(document).ready(function(){
  $('input.autocomplete').autocomplete({
    data: {
      "Apple": null,
      "Microsoft": null,
      "Google": 'https://placehold.it/250x250'
    }
  });
    });    
  }
}
</script>
