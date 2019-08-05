<script>
  export let name;
  const yeastAsProportionOfFlour = 0.002;
  const saltAsProportionOfFlour = 0.03;

  let numberOfDoughBalls = 1;
  let weightOfEachBall = 250;
  let waterPercentage = 57;

  $: flour =
    (numberOfDoughBalls * weightOfEachBall) /
    (1 +
      waterPercentage / 100 +
      yeastAsProportionOfFlour +
      saltAsProportionOfFlour);
  $: water = (flour * waterPercentage) / 100;
  $: salt = flour * saltAsProportionOfFlour;
  $: yeast = flour * yeastAsProportionOfFlour;
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Pizza dough!</h1>

<ul>
  <li>flour {flour.toFixed(1)}</li>
  <li>water {water.toFixed(1)}</li>
  <li>salt {salt.toFixed(1)}</li>
  <li>yeast {yeast.toFixed(1)}</li>
</ul>
