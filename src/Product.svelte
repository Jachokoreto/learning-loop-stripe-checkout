<script>
    let stripe = Stripe('pk_test_51KKzypBmQ1sDTVq1vtpheUz4qQJyFgC1uz4kKH4ZyIzuWeFdgsyzqDvv6Zjbw1PQwnc8sIgpCWHYMG0qA0O0Dl8U003WW5qx1a');

    export let amount;
    export let name;
    export let price;

    // Basic Checkout

    async function startCheckout() {

        const { error } = await stripe.redirectToCheckout({
            lineItems: [{ price, quantity: 1 }],
            mode: 'payment',
            successUrl:'http://localhost:8080',
            cancelUrl: 'http://localhost:8080',
        });

        if (error) {
            alert('out payment system is broken!');
        }
    }
</script>

<section>
    <p>Stripe Checkout</p>

    <div>
    <h2>Healthy Salad <i>🥗</i></h2>
    <p>For some healthy treats, eat salad and beet</p>
    <img src="healthy_salad.jpg" alt="a pic of healthy salad"/>
    </div>
    <button on:click={startCheckout}> Eat Healthy With Just ${amount / 100} </button>
</section>

<style>
    div {
        width: 100%;
        background-color: #e0e7da;
        padding: 8px 16px
    }
    img {
        width: 100%;
        max-width: 500px;
        height: auto;
        margin-bottom: 19px;
    }
   button {
        margin: 8px;
        border: 2px solid  #FEFDD6;
        border-bottom-left-radius: 10px;
        border-top-right-radius: 10px;
        padding: 8px 16px;
        background-color: #4F7942;
        font-size: 2rem;
        color: #ECFFDC;
        cursor:pointer;
   }
</style>