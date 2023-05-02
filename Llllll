import com.stripe.Stripe;
import com.stripe.exception.StripeException;
import com.stripe.model.Charge;

public class PaymentProcessor {
    private static final String STRIPE_SECRET_KEY = "your_stripe_secret_key_here";

    public boolean processPayment(String token, int amount) {
        try {
            Stripe.apiKey = STRIPE_SECRET_KEY;

            // create charge object with the token and the amount
            Charge charge = Charge.create(
              new HashMap<String, Object>(),
              new HashMap<String, Object>()
                .put("amount", amount)
                .put("currency", "usd")
                .put("source", token)
            );

            // payment successful
            return true;
        } catch (StripeException e) {
            // payment failed
            e.printStackTrace();
            return false;
        }
    }
}
