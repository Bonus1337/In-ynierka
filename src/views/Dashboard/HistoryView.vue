<template>
  <v-timeline class="px-5">
    <v-timeline-item
      v-for="(step, i) in steps"
      :key="i"
      :color="step.color"
      small
    >
      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold ${step.color}--text`"
          v-text="step.step"
        ></span>
        {{ step.date }}
      </template>
      <div class="py-3">
        <h2
          :class="`font-weight-light mb-3 ${step.color}--text`"
          v-text="step.header"
        ></h2>
        <div>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis ex
          at ligula facilisis ullamcorper. Integer consequat, augue quis
          malesuada scelerisque, magna enim venenatis nunc, ut posuere arcu dui
          ut diam. Fusce sit amet mi ante. Aenean commodo elementum eros,
          pulvinar pharetra ipsum semper sodales. Suspendisse condimentum eros
          eu urna convallis, sed maximus ligula pellentesque. Etiam non ornare
          dui. Praesent bibendum ut urna nec consectetur. Nunc elementum erat
          eget neque vulputate, a maximus ipsum malesuada. Donec consequat
          sagittis quam, condimentum bibendum dolor porta quis. Quisque
          faucibus, enim a venenatis varius, justo sem pulvinar enim, ac
          volutpat arcu orci a purus. In at volutpat metus. Aenean euismod
          lacinia blandit. Ut vitae quam nec erat ullamcorper volutpat semper ut
          lectus. Quisque interdum convallis nibh vel porttitor. Morbi fringilla
          pulvinar ornare. Integer quis turpis suscipit, laoreet turpis et,
          fermentum odio.
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  data() {
    return {
      steps: [
        {
          color: "black",
          step: "Po pierwsze",
          header: "Skontaktuj się z opiekunem praktyk",
          text: "asdasdaasdasdasdsgfsdadsadasdasdaasdasdasdsgfsdadsadasdasdaasdasdasdsgfsdadsadasdasdaasdasdasdsgfsdadsad",
        },
        {
          color: "green",
          step: "Po drugie",
          header: "Znajdź miejsce praktyk",
          text: "hellodsadasddfgdfsgdfsgdsfgdfasdasdaasdasdasdsgfsdadsadsgdsfgdsfsadsadsad",
        },
      ],
    };
  },
};
</script>

<style scoped>
.wrapped-text {
  white-space: pre-wrap;
}
</style>
