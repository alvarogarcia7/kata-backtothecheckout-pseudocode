let beans = new Product(beans, 0.65)
cart.price([beans]) => 0.65
cart.price([beans, beans]) => 2*0.65 
cart.price([beans, beans, beans]) => 1 // Not 3*0.65
