<script>
  import Product from "./Product.svelte";

</script>

  
<main>
  <h1>My Svelte Store</h1>

  <Product amount={1000} name={'Salad'} price={'price_1KL0T8BmQ1sDTVq1nxLmTC4R'} />
</main>

<style>
  main {
    text-align: center;
    max-width: 240px;
    margin: 0 auto;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
