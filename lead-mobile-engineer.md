# Lead Mobile Engineer

## 1. Consuming APIs with style

Create a simple app (min iOS version: 6) able to consume a JSON API (`/products/`) returning a list of objects as follows:

``` javascript
{
	id: <int>,
	sku: <string>,
	productName: <string>,
	brandName: <string>,
        image: <url>
	price: <int>
	productPage: <url>
}
```

The API accepts 2 params: 

* `from`: a product ID to start from
* `count`: how many products my consumer wants to retrieve

For example:

```
/produts/?from=100&count=50
```

You app should:

* consume the API displaying it with an infinite scrolling mechanism
* persist the objects in a cache used when the app is started/restarted
* when a table row is tapped it will open the product's details (productPage url) in a webview

Also: the opened webpage might send a message to the app by setting its location to:

```
namshi://?message=<string>
```

* catch that message and display it.

### Bonus points :)

* search product by either name or brand name
* universal app resizing the view accordingly to iPhone, iPad and iPad mini using `autoLayout`

### Clarifications

The API is not available online, you don't even have to mock it, simply pretend it exists.

We don't  need a working application but we'd rather like to asses your coding standards, style and software design skills.

There is no time limitation for this challenge.
