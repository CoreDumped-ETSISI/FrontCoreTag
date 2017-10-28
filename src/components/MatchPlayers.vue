<<template>
    <div class="teamMatchup">
      <p>Choose your nickname: </p>

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
