# node-fastbill-automatic

[![Circle CI](https://circleci.com/gh/veyo-care/node-fastbill-automatic/tree/master.svg?style=svg)](https://circleci.com/gh/veyo-care/node-fastbill-automatic/tree/master)

Complete and tested ES6 client for the fastbill automatic API

Last tested on node v5.3.0

# quick start

    npm install node-fastbill-automatic

# available methods

The module exposes API functionality for customers, invoices and subscriptions.
Access through fastbill.customer, fastbill.invoice or fastbill.subscription (like in the example below).

# first example

    'use strict';
    import Fastbill from 'node-fastbill-automatic';
    
    const fastbill = Fastbill.instantiate(
        {
            email: 'YOUR_FASTBILL_EMAIL',
            apikey: 'YOUR_FASTBILL_API_KEY'
        }
    );
    
    // 1. create a customer
    fastbill.customer.create(
      {
        CUSTOMER_NUMBER: 1,
        CUSTOMER_TYPE: 'consumer',
        FIRST_NAME: 'Max',
        LAST_NAME: 'Michael'
    })
    .then(function(customerId){
        console.log(`The customer's fastbillId is ${customerId}`);
        })
    .catch(function(err){
        throw new Error('Customer creation failed');
    });
    
# development

1. Download the repository

2. Install dependencies

```
npm install
```

3. Install babel

```
npm install babel -g
```

4. Run tests

```
npm test
```

5. Run ESLint

```
npm lint
```
