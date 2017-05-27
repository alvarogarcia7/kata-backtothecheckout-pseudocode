Cart (discount) {
  price(products) {
    let discounted = discount.apply(products);
    if(discounted.isPresent()){
      return discounted.get();
    }
    return products.length*products[0].price();
  }
}

Product(name, measure, pricingStrategy){
  price() {
    return pricingStrategy(measure);
  }
}

PricingStrategy(fn) {
  return fn
}
