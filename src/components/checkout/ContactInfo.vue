<template>
  <v-stepper-content step="1">
    <v-text-field
      v-model="data.name"
      :rules="[rules.required]"
      label="Name"
      required
    />
    <v-text-field
      v-model="data.email"
      :rules="[rules.required]"
      label="E-mail"
      required
    />
    <v-text-field
      v-model="data.phone"
      :rules="[rules.required, rules.phone]"
      label="Phone Number"
      required
    />
    <v-btn color="primary" @click="next">Continue</v-btn>
    <v-btn text @click="$router.replace({ name: 'Cart' })">Cancel</v-btn>
  </v-stepper-content>
</template>

<script>
export default {
  props: {
    next: Function,
    rules: Object,
    data: Object,
  },
};
</script>

<style>
</style>