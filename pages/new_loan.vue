<template>
  <div class="main-container w-100" :style="{height: deviceHeight + 'px'}">
    <div class="w-100 boxex-1 bg-blue":style="{height:boxex1Height + 'px'}"></div>
    <div class="w-100 boxex-2 pa-2":style="{height:boxex2Height + 'px'}">
      <div class="loan-1 w-100  d-flex  ga-2" >
        <div class="w-100"><v-text-field label="SF-AA--" variant="solo"></v-text-field></div>
        <div class="w-100 d-flex justify-center"><p class="text-blue text-center text-h6 mt-2">New Loan</p></div>
        <div class="w-100"> <v-date-input label="00-00-0000" prepend-icon="" variant="solo"></v-date-input></div>
      </div>
      <div class="loan-2 w-100 d-flex  ga-10 justify-center align-center  " >
        <v-checkbox class="text-h6" label="Gold"></v-checkbox>
        <v-checkbox class="text-h6" label="Silver"></v-checkbox>
        <v-checkbox class="text-h6" label="Brass"></v-checkbox>
      </div>

      <div class="loan-3 w-100" >
        <v-form v-model="valid">
          <v-container class="pa-0">
              <v-row no-gutters>
                <v-col>
                  <v-sheet class="ma-2 d-flex flex-column ga-4">
                    <v-text-field
                      v-model="loanvalue"
                      :counter="10"
                      :rules="loanRules"
                      label="Loan Value:"
                      placeholder="0.00"
                      hide-details
                      required
                      class="w-100"
                    ></v-text-field>
                    <v-text-field
                      v-model="loanhandover"
                      :counter="10"
                      :rules="loan_hand_overRules"
                      label="Loan Handover:"
                      placeholder="0.0"
                      hide-details
                      required
                      class="w-100"
                    ></v-text-field>
                    <v-text-field
                      v-model="weight"
                      :counter="10"
                      :rules="weightRules"
                      label="Weight:"
                      placeholder="000.000"
                      hide-details
                      required
                      class="w-100"
                    ></v-text-field>
                  </v-sheet>
                </v-col>
                <v-col>
                  <v-sheet class="ma-2">
                    <div class="w-100 d-flex flex-column pa-2">
                        <h5>Porul:</h5>
                        <div class="card pa-2 d-flex flex-column justify-center align-center ga-3 rounded-lg bg-grey-lighten-3 w-100">
                          <v-icon icon="mdi-file-upload" class="text-h4"></v-icon>
                          <p class="text-center">Drag and drop <br> File Here</p>
        
                          <v-btn   class="bg-red rounded-lg text-white" >Browser File</v-btn>
                        </div>
                      </div>
                  </v-sheet>
                </v-col>
              </v-row>

              <v-row no-gutters class="mt-2">
                <v-col>
                  <v-sheet class="ma-2">
                    <v-text-field
                      v-model="pawn"
                      :counter="10"
                      :rules="pawnRules"
                      label="Pawn_Details:"
                       placeholder="English / தமிழ்"
                      hide-details
                      required
                    ></v-text-field>
                  </v-sheet>
                </v-col>
              </v-row>  
            </v-container>
        </v-form>
      </div>
    </div>

    <div class="w-100 d-flex ga-3 pa-4 align-center" :style="{height:boxex3Height + 'px'}">
        <div class="w-100"><v-btn class="bg-yellow text-black" block>Reset</v-btn></div>
        <div class="w-100"><nuxt-link to="/loan_success" style="text-decoration: none;"><v-btn class="bg-green text-white" block>Proceed For Esign</v-btn></nuxt-link></div>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      deviceWidth: 0,
      deviceHeight: 0,
      boxex1Height: 0,
      boxex2Height: 0,
      boxex3Height: 0
      

    };
  },
  mounted() {
    this.updateDeviceDimensions(); // Initial call to set dimensions on component mount
    window.addEventListener('resize', this.updateDeviceDimensions); // Listen for window resize events
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateDeviceDimensions); // Clean up: remove resize event listener
  },
  methods: {
    updateDeviceDimensions() {
      this.deviceWidth = window.innerWidth; // Update device width
      this.deviceHeight = window.innerHeight; // Update device height

      // Calculate heights for each boxex based on percentages
      this.boxex1Height = Math.floor(this.deviceHeight * 0.05); // 6% of device height
      this.boxex2Height = Math.floor(this.deviceHeight * 0.90); // 88% of device height
      this.boxex3Height = Math.floor(this.deviceHeight * 0.05); // 6% of device height
     
    },
    

  }
};
</script>

<style scoped>



</style>
