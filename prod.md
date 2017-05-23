Cart (strategy) {
  price(products) {
    let discounted = strategy.apply(products);
    if(discounted.isPresent()){
      return discounted.get();
    }
    return products.length*products[0].price();
  }
}

Product(name, price){
  price() {
    return price
  }
}

