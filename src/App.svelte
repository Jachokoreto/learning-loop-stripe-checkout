<script>
  import Product from "./Product.svelte";

</script>



<h1>My Svelte Store</h1>

<Product amount={1999} name={'Salad'} price={'price_1KL0T8BmQ1sDTVq1nxLmTC4R'} />

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
