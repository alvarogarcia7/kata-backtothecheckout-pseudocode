let beans = new Product(beans, new PricingStrategy(()=>0.65))
let cart = new Cart(new 3For1DollarDiscount());
cart.price([beans]) => 0.65
cart.price([beans, beans]) => 2*0.65 
cart.price([beans, beans, beans]) => 1 // Not 3*0.65
