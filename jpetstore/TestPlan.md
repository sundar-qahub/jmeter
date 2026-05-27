##Objective
---------
The following are the objective of this test 
- to measure the performance of the application Jpetstore by conducting load test
- The response time of the test should be within acceptable limits (assume to be 3 seconds for each page load)
- Identify any performance issues while running and analyzing the test

##Scope
------
The scope of the test is to conduct load testing on the Jpetstore application and measure its performance. 

As the servers in the application are not accessible, the metrics of the web server, application server and db server for Jpetstore application are not monitored during the test

##Test Scenarios
--------------
The following scenarios are identified as important workflows to be considered for the performance testing of the Jpetstore application
| No | Scenario |
| --- | --- |
| 1 | Buy Fish |
| 2 | Buy Cats |
| 3 | Buy Reptiles |
| 4 | Buy Birds |
| 5 | Buy Dogs |
| 6 | Buy two different pets |
| 7 | Search and buy |
| 8 | Search and Add to cart |
| 9 | Login and Logout |


The following are the detailed steps in each scenarios

**Scenario 1**: Buy Fish
 a) Launch the application
 b) Enter the store
 c) Click Signin link
 d) Enter username/password and click Login
 e) Click Fish
 f) Select one of the fish product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Sign out

**Scenario 2**: Buy Cats
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Click Cats
 f) Select one of the cat product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Signout

**Scenario 3**: Buy Reptiles
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Click Reptiles
 f) Select one of the reptile product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Signout

**Scenario 4**: Buy Birds
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Click Birds
 f) Select one of the bird product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Signout

**Scenario 5**: Buy Dogs
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Click Dogs
 f) Select one of the dog product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Signout

**Scenario 6**: Buy two different pets
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Click one of the pet
 f) Select one of the product
 g) click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Click "Return to main menu"
 j) Select different pet
 k) Select one of the product
 l) click AddToCart
 m) Enter the payment details and click Continue
 n) Confirm the order
 o) In the confirmation page, click Signout

**Scenario 7**: Search and Buy
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Enter the product name in the Search box
 f) Click on the product
 g) select the item from product and click AddToCart
 h) Update Quantity at random and Proceed to Checkout
 i) Enter the payment details and click Continue
 k) Confirm the order
 l) In the confirmation page, click Signout

**Scenario 8**: Search and Add to cart
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) Enter the product name in the Search box
 f) Click on the product
 g) select the item from product and click AddToCart
 l) In the confirmation page, click Signout

**Scenario 9**: Login and Logout
 a) Launch the application
 b) Enter the store
 c) Click Signin
 d) Enter username/password and click Login
 e) click Signout

NOTE: After each page load, the page need to be asserted in the Jmeter script

##Test approach
-------------
Each Scenario will take 60 seconds to ramp up, maintain a steady state for 3600 seconds (1 hour) and 60 seconds to ramp down

Total of 30 users are considered for the testing

The following number of users are used for perfomance testing of each scenarios
| Scenario No | Scenario Name | Users | Assumption |
| --- | --- | ---  | ---|
| 1 | Buy Fish | 8 | Low cost, easy and impulsive buyers |
| 2 | Buy Cats | 4 | Popular among apartment owners |
| 3 | Buy Reptiles | 1 | Speciality hobby |
| 4 | Buy Birds | 2 | Low or Moderate interest for this pets |
| 5 | Buy Dogs | 5 | Popular among pet owners who can afford |
| 6 | Buy two different pet | 6 | Multiple pet buyers |
| 7 | Search and buy | 2 | Very few users will search for a particular pet to buy |
| 8 | Search and Add to cart | 1 | Some users search and leave the cart before buying |
| 9 | Login and Logout | 1 | Login,look at the home page and Logout without browsing other pages|

##Test Data
---------
The following are the test data used for the test
a) 30 unique set of users created and shared among all test scenarios
b) Scenarios use ProductID for Fish, Cat, Reptiles, Birds and Dogs for selecting the product
c) Scenarios use ItemsID for sub categories of pets in the product
d) Quantity of the Item in the card will be updated randomly between 1 to 3 while buying pets
e) Name of the items in all the products will be used for search and adding to cart step in scenarios

##Metrics to be Monitored
------------------------
a) Throughput
b) Response time (Min/Max/Avg)
c) 90%, 95% and 99% response time percentiles
d) Error rate
