# Coding Challenge for SALIDO Rails Engineer

This challenge is provided to help assess a candidate's development skills. There is no time limit, but we ask that you be prompt in submitting your solution.

## Submission Instructions

1. Complete the challenge according to the Challenge Instructions below.
1. Deploy your code on the internets so we can see it in action.
1. Create a GitHub repository and push your code to it.
1. Include a README in your repository to explain and document your solution.
1. Send an email to challenge-accepted@salido.com that includes links to your live solution and to your GitHub repository.

## Tech Stack Requirements

* Database: **MongoDB** (https://www.mongodb.org)
* Language: **Ruby** (https://www.ruby-lang.org)
* Framework: **Rails** (http://rubyonrails.org)
* Object Document Mapper: **Mongoid** (http://mongoid.org)
* Testing: **Rspec** (http://rspec.info)

## Challenge Instructions

### Objective
Create a basic Rails app that sources data from a 3rd party API and presents a nice UI for a user to interact with the data.

### Business Requirements

* Imagine SALIDO has just acquired a wine distribution company. We need to source product data from the wine.com API (http://api.wine.com) and load it into our own database of wine products.
* The user should be able to update and delete existing wine products, as well as create new ones in our local database.
* The user should be able to search for wine products in our database.
* The user should be able to easily load and reload fresh data from the wine.com API via a web UI.
* When loading/reloading data from the wine.com API, it must not delete or overwrite products that were added directly to our local database by a user.
* When loading/reloading data from the wine.com API, it should delete/overwrite products from the wine.com API even if a user has modified the information on those products.

### To Do

1. Create the appropriate data models to store wine products based the wine.com API Object Dictionary (https://api.wine.com/wiki/api-object-dictionary).
  * NOTE: Your models need *not* be comprehensive. Just the basic product data will do.
2. Create a very basic web UI that does the following:
  * CRUD a wine product.
  * Present a view showing a paginated, searchable list of wine products.
    * This view should have a search box at the top that will filter the list as the user types.
  * Present a view that allows the user to load data from the wine.com API. This view should:
    * Present a button that clears out the existing wine.com data (but leaves the user-submitted data intact).
    * Present a button that loads fresh data from the wine.com API. This should overwrite any existing wine.com data in our database.
    * When a button is pressed, use AJAX and present the user with some sort of modal "loading" indicator until the operation is complete.
3. Write some basic Rspec tests for your code.
