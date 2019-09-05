<template>
  <v-container>
    <v-layout text-center wrap>
      <v-card width="200" class="mx-auto" >
        <v-form v-model="valid">
          <v-container>
            <v-row>
              <v-col cols="12" md="12">
                ¿Es primo?
                <v-text-field
                  type="number"
                  v-model="num"
                  label="Número"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
        </v-form>
        <v-card-actions>
          {{numeroPrimo}}
        </v-card-actions>
      </v-card>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    num : ''
  }),
  methods: {
  },
  computed: {
    numeroPrimo () {
      let number = parseInt(this.num);

      if(!number) { return; }

      for (var i = 2; i < number; i++) {
        if (number % i === 0) { return '🚀'; }
      }

      return number !== 1 ? '🐵' : '🚀';
    }
  }
};
</script>
