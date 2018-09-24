<template>
  <div>
    <div class="md-layout md-gutter">
      <div class="md-layout-item">
        <md-field>
          <label for="movie">Movie</label>
          <md-select
            v-model="handleSelection"
            :value="movie"
            name="movie"
          >
            <md-option value="cycki" asd>💩💩💩</md-option>
            <md-option value="godfather">Godfather</md-option>
            <md-option value="godfather-ii">Godfather II</md-option>
            <md-option value="godfather-iii">Godfather III</md-option>
            <md-option value="godfellas">Godfellas</md-option>
            <md-option value="pulp-fiction">Pulp Fiction</md-option>
            <md-option value="scarface">Scarface</md-option>
          </md-select>
        </md-field>
      </div>
    </div>

    <md-button class="md-primary md-raised" @click="movie = 'pulp-fiction'">Set Pulp Fiction</md-button>
  </div>
</template>

<script>
  export default {
    name: 'BasicSelect',
    data: () => ({
      movie: 'godfather',
      country: null,
      font: null
    }),
    computed: {
      // custom option for handling selected options
      // should allow to defer different cases
      handleSelection: {
        get() {
          return this.datesRange;
        },
        set(value) {
          // debugger;
          if (value === 'cycki') {
            console.log('lets do it');
            this.$emit('md-closed')

            return;
          }

          // reproduced same behaviour as with default select option
          // provided by vue-material
          // const selectedOption = this.options.find((obj) => obj.key === value);
          // this.dateRange = selectedOption.value;

          // return this.dateRange;
        },
      },
    }
  }
</script>
