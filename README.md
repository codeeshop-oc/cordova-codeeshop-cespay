# Code-E-Shop Custom Payment Gateway Integration Cordova Plugin

Cordova Custom Payment Gateway Integration with In-App Browser

This Cordova plugin helps you to be able to use any Payment Gateway haveing Succeess and Failed Callback URL to return response with your Cordova hybrid application. This plugin supports Android.

## Installation:

Add another dependent cordova plugin 
[cordova-plugin-inappbrowser](https://www.npmjs.com/package/cordova-plugin-inappbrowser)
`cordova plugin add cordova-plugin-inappbrowser`

Add this plugin in your cordova application with the following command.

`cordova plugin add cordova-codeeshop-cespay`

It is also possible to install the plugin via repo url directly

`cordova plugin add https://github.com/codeeshop-oc/cordova-codeeshop-cespay.git`

## Usage:

```
// Init Payment
CustomPayment.startPayment({
  url: 'YOUR_PAYMENT_REDIRECT_URL', 
  callbackErrorURL: 'YOUR_PAYMENT_FAILURE_URL', 
  callbackSuccessURL: 'YOUR_PAYMENT_SUCCESS_URL'
})

// Return Payment Response Event
window.addEventListener('paymentmessage', this.paymentCallBack)

function paymentCallBack(e) {
  if(typeof e.detail != 'undefined') {
    console.debug(e.detail.data, 'paramsparams1')
  } else {
    console.debug(e, 'other paramsparamsparams')
  }
}
```
## Live Demo

[![Youtube Link](https://img.youtube.com/vi/AoRvwAklZaQ/0.jpg)](http://www.youtube.com/watch?v=AoRvwAklZaQ)

### All Params

Method: startPayment

| Prop name          | Description                                      | Type    | Values                   | Default      |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | --------------------- | ------------ |
| url                | YOUR_PAYMENT_REDIRECT_URL                        | String  | -                        |     |
| target             | key to be used to show listing data ( just one ) | String  | -                        | _blank |
| options            | Cordova Plugin Options ( cordova-plugin-inappbrowser ) | String  | [Options](https://github.com/apache/cordova-plugin-inappbrowser#example-1)       | location=no,hidenavigationbuttons=yes,hideurlbar=yes,hardwareback=no,fullscreen=yes        |
| callbackSuccessURL | YOUR_PAYMENT_FAILURE_URL                        | String  | -                | success      |
| callbackErrorURL   | YOUR_PAYMENT_SUCCESS_URL                      | String  | - | failed       |

## ???? License

This software is licensed under the [MIT](https://github.com/codeeshop-oc/vue-full-autocomplete/blob/main/LICENSE).
