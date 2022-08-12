# Payunit

This gem was developed to aid Cameroon businesses to make both national and international payments using MTN and Orange Mobile Money, Paypal, Credit Card and Express Union.

## Installation

Install the gem and add to the application's Gemfile by executing:

    $ bundle add payunit

If bundler is not being used to manage dependencies, install the gem by executing:

    $ gem install payunit

## Usage
Follow the instructions below to make payments locally:
- Create an account on `https://app.payunit.net/#/` to obtain your api_key, api_password, api_username 
- Add ```gem 'payunit', '~> 0.1.0'``` to your gemfile
- Add `gem 'dotenv-rails', '~> 2.8', '>= 2.8.1'` to your gemfile in order to save your secret credentials

- Create a PayUnit Class and call the payment method
```payment = PayUnit.new(api_key, api_username, api_password, return_url, notify_url, mode, currency)```

- Next is ```payment.make_payment(amount)```

- The ```pay.make_payment()``` have optional parameters such as:
- ```
    @purchaseRef = purchaseRef
    @description = description
    @name = name
```
The above parameters are acceptable by payunit but they are optional and needs to be passed as ```payment.make_payment(amount, purchaseRef, description, name)```

- The above code will open a payment url that will be used to make the payment
- Make payments anywhere in your rails app by running the following
1. payment = PayUnit.new(ENV(api_key), ENV(api_username), ENV(api_password), return_url,notify_url, mode, currency)
2. payment.payment.make_payment(amount)
# Note
- Amount is an integer gotten from the user
- Notify url is the success url to redirect to when the request is successful 
- Return url is the url to return to when the request fails
- Mode is the the environment of the payment whether it is test or live
- Currency the country currency the payment will be made in 


### ✒️ Authors

👤 **Stanley Enow Lekunze**

- Github: [@happiguru](https://github.com/happiguru)
- LinkedIn:[LinkedIn](https://www.linkedin.com/in/lekunze-nley)

👤 **CHE NSOH BLANCHARD**

- GitHub: [@che30](https://github.com/che30)
- Twitter: [@BlanchardNsoh](https://twitter.com/che55085128 )
- LinkedIn: [Che Blanchard](https://www.linkedin.com/in/che-nsoh-9455271b0/)

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[happiguru]/payunit. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](https://github.com/[happiguru]/payunit/blob/main/CODE_OF_CONDUCT.md).

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Payunit project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/payunit/blob/main/CODE_OF_CONDUCT.md).
