You are working at a bank and are tasked to rewrite some
of their APIs -- in particular, you will now need to write
the code that transfer money between 2 accounts.

The bank employs this DB structure:

```
TABLE transactions
  - reference (unique)
  - amount
  - account nr

TABLE balances
  - account nr (unique)
  - balance
```

The transaction table registers any transaction in an account
(ie. today I paid 20$ for a movie with my credit card), the
balances table represents the account balance of customers
(ie. I have $5k in my bank account).

The bank uses a relational DB to store these info (say MySQL)
and you are tasked to port the "transfer API" from an old
framework to NodeJS. Here's how your code starts to look like:

``` js
app.post('/transactions', (req, res) => {
  // here starts the fun
})
```

Can you implement this API? You do not need a working code
example (ie. we're not asking you to setup a DB for this challenge),
but we would like to see near production-ready code. If you feel
you'd do better with a working app, feel free to do so.

The route we're asking you to implement receives a transfer request
(`{from: account, to: account, amount: money}`) and updates the
transactions / balances table accordingly.

A few things to keep in mind:

* you will receive requests from the bank's mobile app, that customers use to transfer money around
* can you deal with the fact that one customer might tap on the "transfer" button twice, by mistake?
* what happens if your database becomes unavailable in the middle of your logic?
* what happens if 2 users (A, B) transfer money to user C at the same time?
* remember that you are working at a bank, so you need to make sure the request and the data you save are always valid and consistent
* the only thing you will not need to validate is that the user is authorized to perform this API request. let's assume the user is logged in and carrier a cookie, with the transfer request, that ensure it comes from a legit source
* please use `async / await` to handle async operations
