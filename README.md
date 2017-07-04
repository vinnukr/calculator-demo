# cashpresso creditcalculator demo

## Requirements

* jquery (tested with version 3.2.1)

## Getting started

See demo.html or demo_small.html for details.

We suggest that you use jqueries onDomReady:
~~~~
$(document).ready(function() {
  CreditCalculator.init({targetSelector:"#c2_creditcalculator_container",language:"de", amount: 1300.75,interestFreeDays:30, partnerId:"5436ed23a2bf5022b18b15be13d347b1",url: "https://this.is.my.shop.com/redirect/bla", format: "small", hideButton: true, mode:"test"});
});
~~~~

## Usage Options

* **targetSelector**: The id of the container, where the cashpresso credit calculator should be loaded.
* **language**: Currently support are _de_, _en_
* **amount** (optional): if specified, freezes the credit amount to the given value
* **interestFreeDays** (optional): number of interest free days the creditcalculator that the partner provides - validated against the partnerApiKey!
* **partnerApiKey** (optional): your Api key is necessary if you are an e-Commerce partner and want to include your additional interest free days in the credit calculation - the Api key is displayed if you login to partner.cashpresso.com (for the test environment: https://test.cashpresso.com/urlreferral/)
* **url** (optional): The url that the "Finance with cashpresso" button should point to! - Specify your affiliate url. E-Commerce partners will probably want to hide this button in favour of their own checkout button! ->
* **hideButton** (optional): true/false - Hides the "Finance with cashpresso" button when true
* **format**: one of_small_/_wide_ - default: _wide_
* **mode**: one of _test_,_live_ - default: _live_

## Working with the calculator
If you want to process the data that the user selected in the calculator, you have two options:
1. Access the javascript variables:  _CreditCalculator.currentAmount_ holds the currently selected amount, _CreditCalculator.currentRate_ holds the selected monthly rate
2. The creditcalculator provides two input fields (hidden) that can be used when the creditcalculator is included in a form  - _amountSlider_ holds the selected credit amount and _paybackRateSlider_ holds the selected monthly rate.

## Layout customization
We use a reduced and simplified bootstrap sample that is prefixed with #c2_creditcalculator (the id of the container we load). The full stylesheet can be found in the [lib-folder](./lib/cashpresso-style.css)!
**Attention**: The creditcalculator loads the stylesheet from cashpresso.com - the css file here is provided only as   documentation!

### Slider customization
This uses the bootstrap-slider by seiyria!
See https://github.com/seiyria/bootstrap-slider for details about customizing the sliders
