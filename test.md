let beans = beansByCan = new Product(beans, {unit: 1}, new PricingStrategy(({unit})=>0.65*unit))
let beansByWeight = new Product(beans, {weight: 1.kg}, new PricingStrategy(({kg})=>2*kg))
let cart = new Cart(new 3For1DollarDiscount());
cart.price([beans]) => 0.65
cart.price([beans, beans]) => 2*0.65 
cart.price([beans, beans, beans]) => 1 // Not 3*0.65

cart.price([beansByWeight]) => 2.0
