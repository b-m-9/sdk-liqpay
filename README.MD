### Installation
```
npm install --save sdk-liqpay
```
require module
```javascript
const Liqpay = require('sdk-liqpay');
```
## Merchant Documentation:
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fmedve-dev%2Fsdk-liqpay.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fmedve-dev%2Fsdk-liqpay?ref=badge_shield)

Init
```javascript
const liqpayMerchant = new Liqpay.merchant('i37338111051', 'Secret', {debug: false});
```
### Create payment
```javascript

liqpayMerchant
    .getOrderId({
        amount: 1,
        currency: 'UAH',
        description: 'MIT SDK NODE TEST'
    })
    .then(res => {
        return liqpayMerchant.formaterData(res);
    })
    .then(res => {
        return liqpayMerchant.createPaymet(res)
    })
    .then(console.log)
    .catch((error) => {
        console.error('Create Error,', error);
    });

```
### Browse function:
```javascript
function payment(param) {
    var method = param.method || "post";
    var form = document.createElement("form");
    form.setAttribute("method", param.method);
    form.setAttribute("action", param.url);
    for (var key in param.data) {
        if (param.data.hasOwnProperty(key)) {
            var hiddenField = document.createElement("input");
            hiddenField.setAttribute("type", "hidden");
            hiddenField.setAttribute("name", key);
            hiddenField.setAttribute("value", param.data[key]);

            form.appendChild(hiddenField);
        }
    }
    document.body.appendChild(form);
    form.submit();
}
```

## Donate: https://www.liqpay.ua/ru/checkout/i37338111051

## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fmedve-dev%2Fsdk-liqpay.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fmedve-dev%2Fsdk-liqpay?ref=badge_large)