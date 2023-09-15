# secondbtc connector in Nodejs



This is a lightweight library that works as a connector to [Secondbtc public API](https://secondbtc.com/en/api/v1). It’s designed to be simple, clean, and easy to use with minimal dependencies.

## Installation

```bash
npm install @secondbtc/api
```

## Documentation

[https://github.com/secondbtcExchange/secondbtc-connector-node/](https://github.com/secondbtcExchange/secondbtc-connector-node)


## RESTful APIs

```javascript

const { Spot } = require('@secondbtc/api')

const apiKey = ''
const apiSecret = ''
const client = new Spot(apiKey, apiSecret);



client.exchangeInfo({ symbol: 'BTCUSDT' }).then((response) => console.log(response.data));

// client.ping().then((response) => console.log(response.data));
// client.time().then((response) => console.log(response.data));
// client.depth().then((response) => console.log(response.data));
// client.ticker().then((response) => console.log(response.data));
// client.tickerPrice().then((response) => console.log(response.data));
// client.bookTicker().then((response) => console.log(response.data));


//New order LIMIT and STOP LIMIT
const options = {
    quantity: 0.0005,
    price: 20279.36,
}
client.newOrder('BTCUSDT', 'SELL', 'LIMIT', options).then((response) => console.log(response.data));


//New order MARKET SELL
// const options = {
//     quantity: 0.0005
// }
// client.newOrder('BTCUSDT', 'SELL', 'MARKET', options).then((response) => console.log(response.data));


//New order BUY 
// const options = {
//     quoteOrderQty: 180.00,
// }
// client.newOrder('BTCUSDT', 'BUY', 'MARKET', options).then((response) => console.log(response.data));


//Cancel Order
// const options = {
//     orderId: 'order_id'
// }
// client.cancelOrder('BTCUSDT', options).then((response) => console.log(response.data));

//Open order list
//client.openOrders({symbol:"BTCUSDT"}).then((response) => console.log(response.data));


//allOrders list
//client.allOrders("BTCUSDT").then((response) => console.log(response.data));


//Trade history list
//client.myTrades("BTCUSDT").then((response) => console.log(response.data));
```



### Base URL

Defaults to `api.secondbtc.com`.