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
    <h2>Stripe Checkout</h2>

    <i>🥗</i>

    <button on:click={startCheckout}> Buy me ${amount / 100} </button>
</section>