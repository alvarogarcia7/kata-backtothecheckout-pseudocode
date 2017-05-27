Cart (discount) {
  price(products) {
    let discounted = discount.apply(products);
    if(discounted.isPresent()){
      return discounted.get()(products);
    }
    return products.length*products[0].price();
  }
}

Discount{
  //apply :: [Product] -> Optional PricingStrategy
  apply(products)
}

3For1DollarDiscount implements Discount {
  apply(products) {
    if(products.length === 3) {
      return Just new PricingStrategy(() => 1)
    }
    return None
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
