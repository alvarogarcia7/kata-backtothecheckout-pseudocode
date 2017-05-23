Cart {
  price(products) {
    return products.length*products[0].price();
  }
}

Product(name, price){
  price() {
    return price
  }
}
