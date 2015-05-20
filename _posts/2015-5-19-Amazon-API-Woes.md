---
layout: post
title: Amazon API Woes
---

We spent the morning in two directions one team setting up the rails environment we are going to work in and my pair spent the morning looking at how we would interact with the third party elements of the project and how we would need to link these together in a holistic way to meet our MVP. We diagramed this out roughly to allow easy communication with the rest of the team and as a way of us understanding the complexity of the interactions.

![Technologies Map](/images/TechnologiesPlan.png)

After updating our backlog by breaking some of the larger tasks down into smaller elements achievable in a days sprint we went about looking at how we can get search results back from Amazon through their Product Advertising API. After setting up the appropriate access keys we were able to access the Scratch Pad to 'play' with responses. From this we realised the scale of the task as the Amazon response to include all the elements we want is a leviathon of an XML response. 

Queue testing, after discovering the variablility and complexity of the Google API response it was obvious that our test coverage would have to be wide. Starting with a feature test in RSpec we hit our first hurdle, how could we stub AJAX calls in RSpec/Capybara feature tests? Our first consideration is maybe we should do these in Jasmine instead then, not ideal in terms of test coverage readability, so after some research we found [Puffing Billy!](https://github.com/oesmith/puffing-billy) A ruby gem that works in selenium and captures external calls and provides methods to return stubs to these. We later swapped to running this with [Poltergeist](https://github.com/teampoltergeist/poltergeist) to speed up the testing process.

```ruby
# Setup in spec/rails_helper.rb

require 'billy/rspec'
require 'capybara/poltergeist'
Capybara.javascript_driver = :poltergeist_billy

# Feature test in spec/feature/...

feature 'adds a gift', js: true do
  context 'searching for an amazon product' do
    scenario 'search products from amazon' do
      proxy.stub('/gifts/search')
        .and_return(json: FORMATTED_RETURN) #FORMATTED_RETURN is the mock JSON object in a helper
      visit '/gifts/new'
      fill_in 'search_keyword', with: 'Macbook Pro'
      click_button('Search')
      expect(page).to have_content('MacBook Pro')
    end
  end
end
```

Great! On to unit testing, our unit tests grew rapidly as we realised the complexity of the Amazon response, at one point we had a 3 person team fighting at getting the tests to pass, with particular problems that rather than returning a null value, if the value does not exist amazon just does not return a key, meaning a data structure that is potentially different from every item. This is where a good test coverage proved itself and after about 8 hours x2/3 people thrown at it we had a robust solution. Goodnight!
