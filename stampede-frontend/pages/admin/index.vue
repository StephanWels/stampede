<template>
  <div>
    <h1 class="mb-4 text-h4">Stamp Import</h1>
    <v-stepper v-if="!done" v-model="currentStep" alt-labels>
    <v-stepper-header>
      <v-stepper-step step="1">
        Upload CSV
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="2">
        Choose Email Column and Campaign
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="3">
        Review and Collect Stamps
      </v-stepper-step>
    </v-stepper-header>
    <v-stepper-content step="1">
      <v-form>
        <v-file-input label="Email CSV"></v-file-input>

        <v-btn @click="currentStep++">Upload</v-btn>
      </v-form>
    </v-stepper-content>

    <v-stepper-content step="2">
      <v-form>
        <v-select label="Loyalty Campaign" value="Feedback Hero" :items="['Feedback Hero', 'IU Coffee Table']">
        </v-select>
        <v-select label="Email Column Name in CSV" value="Created At" :items="['Created At','Email','First Name','Last Name']">
        </v-select>

        <v-btn @click="currentStep++">Review</v-btn>
      </v-form>
    </v-stepper-content>
    <v-stepper-content step="3">
      <v-form>
        <h2 class="text-h5">Import Result Preview</h2>
        <div class="text-body-1"><b>1932</b> Emails found.</div>
        <div class="text-body-1"><b>510</b> Will receive their first Stamp.</div>
        <div class="text-body-1"><b>451</b> Will receive their second Stamp.</div>
        <div class="text-body-1"><b>...</b></div>
        <div class="text-body-1"><b>71</b> Will receive their final Stamp. Hooray! Merch incoming!</div>

        <v-btn @click="done=true">Collect Stamps</v-btn>
      </v-form>
    </v-stepper-content>
  </v-stepper>
    <div class="rounded-xl success d-flex flex-column justify-space-around" v-else>
      <v-icon size="9rem">mdi-check-all</v-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data: () => {
    return {
      currentStep: 1,
      done:false
    }
  }
}
</script>

