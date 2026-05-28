## Objective
The following are the objective of this test 
- To measure the performance of the application Jpetstore by conducting load test
- The response time of the test should be within acceptable limits (assume to be 3 seconds for each page load)
- Identify any performance issues while running and analyzing the test

## Scope
The scope of the test include conducting load testing on the Jpetstore application and measure its performance. 

As the servers in the application are not accessible, the metrics from web server(s), application server(s) and db server(s) are not monitored during the test

## Test Scenarios
The following scenarios are identified as important workflows for performance testing of Jpetstore application
| No | Scenario |
| --- | --- |
| 1 | Buy Fish |
| 2 | Buy Cats |
| 3 | Buy Reptiles |
| 4 | Buy Birds |
| 5 | Buy Dogs |
| 6 | Buy multiple pets (only considering two pets) |
| 7 | Search and buy |
| 8 | Search and Add to cart |
| 9 | Login and Logout |


The following are the detailed steps in each scenarios

**Scenario 1**: Buy Fish
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click on pet "Fish" link or image
 f) Select one product from pet Fish
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 J) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 2**: Buy Cats
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click on pet "Cats" link or image
 f) Select one product from pet Cat
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 j) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 3**: Buy Reptiles
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click on pet "Reptiles" link or image
 f) Select one product from pet Reptile
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 j) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 4**: Buy Birds
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click on the pet "Birds" link or image
 f) Select one product from pet Bird
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 j) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 5**: Buy Dogs
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click on the pet "Dogs" link or image
 f) Select one product from pet Dogs
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 j) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button 
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 6**: Buy Multiple pets
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Click one of the pet
 f) Select one product from the selected pet
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Return to Main Menu" link
 j) Select a different pet
 k) Select one product from selected pet
 l) Click "Add to Cart" on one item
 m) Enter the payment details and click "Continue" button
 n) Confirm the order by clicking "Confirm" button
 o) In the confirmation page, click "Sign Out" link
```

**Scenario 7**: Search and Buy
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Enter the specific product in the Search box and click "Search" button
 f) Select one of the product from the result
 g) Click "Add to Cart" on one item
 h) Update random quantity and click "Update Cart" button
 i) Click "Proceed to Checkout" button
 j) Enter the payment details and click "Continue" button
 k) Confirm the order by clicking "Confirm" button
 l) In the confirmation page, click "Sign Out" link
```

**Scenario 8**: Search and AddToCart
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter Username/Password and click "Login" button
 e) Enter the specific product name in the Search box and click "Search" button
 f) Select one of the product from the result
 g) Click "Add to Cart" on one item
 l) Click "Sign Out" link
```

**Scenario 9**: Login and Logout
```
 a) Launch the application
 b) Click on "Enter the Store" link
 c) Click "Sign In" link
 d) Enter username/password and click Login
 e) wait for 30 seconds
 e) Click "Sign Out" link
```

**NOTE**: After each page load, the page need to be asserted in the Jmeter script

## Test approach
Each Scenario will take 60 seconds to ramp up, maintain a steady state for 3600 seconds (1 hour) and 60 seconds to ramp down

Total of 30 users are considered for the testing

The following is the workload distrubtion considered for the scenarios
| Scenario No | Scenario Name | distribution | Assumption |
| --- | --- | ---  | ---|
| 1 | Buy Fish | 26.7% | Low cost, easy and impulsive buyers |
| 2 | Buy Cats | 13.3% | Popular among apartment owners |
| 3 | Buy Reptiles | 3.3% | Speciality hobby |
| 4 | Buy Birds | 6.7% | Low or Moderate interest for this pets |
| 5 | Buy Dogs | 16.7% | Popular among pet owners who can afford |
| 6 | Buy two different pet | 20% | Multiple pet buyers |
| 7 | Search and buy | 6.7% | Very few users will search for a particular pet to buy |
| 8 | Search and Add to cart | 3.3% | Some users search and leave the cart before buying |
| 9 | Login and Logout | 3.3% | Login,look at the home page and Logout without browsing other pages|

## Workload Model
The workload modelling of a scenario should satisfy Little's Law
```
Number of Users = (scenario processed)/sec * (Response time + think time + pacing) 
```

Let's assume petstore process a scenario every 2 seconds (i.e., scenarios processed/sec is 0.5)

The following table list the distribution of users and iteration time of each scenario's

| Scenario No | Scenario Name | Percentage of total load | Users | Scenario Processed/sec | Response Time + Think time + Pacing |
| --- | --- | --- | --- | --- | --- |
| 1 | Buy Fish | 26.67% | 8 | 0.13 | 61 | 
| 2 | Buy Cats | 13.3% | 4 | 0.067 | 59 |
| 3 | Buy Reptiles | 3.3% | 1 | 0.017 | 58 |
| 4 | Buy Birds | 6.7% | 2 | 0.034 | 58 |
| 5 | Buy Dogs | 16.7%| 5 | 0.084  i 59 |
| 6 | Buy two different pet | 20% | 6 | 0.1 | 60 |
| 7 | Search and buy | 6.7% | 2 | 0.034 | 58 |
| 8 | Search and Add to cart | 3.3%| 1 | 0.017 | 58 |
| 9 | Login and Logout | 3.3% | 1 | 0.017 | 58 |

## Test Data
The following are the test data used for the test
- 30 unique set of users created and shared among all test scenarios
- Scenarios use ProductID for Fish, Cat, Reptiles, Birds and Dogs for selecting the product
- Scenarios use ItemsID for sub categories of pets in the product
- Quantity of the Item in the card will be updated randomly between 1 to 3 while buying pets
- Name of the items in all the products will be used for search and adding to cart step in scenarios

## Metrics Monitored
- Throughput
- Response time (Min/Max/Avg)
- 90%, 95% and 99% response time percentiles
- Error rate
