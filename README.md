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
Build a Rails app that sources data from a 3rd party API and provides a clean and usable UI to interact with the data.

### Business Requirements

* Imagine SALIDO has just acquired a wine distribution company. We need to source product data from the wine.com API (http://api.wine.com) and load it into our own database of wine products.
* The user should be able to update and delete existing wine products, as well as create new ones in our local database.
* The user should be able to search for wine products in our database.
* The user should be able to easily load and reload fresh data from the wine.com API via a web UI.
* When loading/reloading data from the wine.com API, it must not delete or overwrite products that were added directly to our local database by a user.
* When loading/reloading data from the wine.com API, it should delete/overwrite products from the wine.com API even if a user has modified the information on those products.

### To Do

1. Create the appropriate data models to store wine products based the [wine.com API Object Dictionary](https://api.wine.com/wiki/api-object-dictionary).
  * Your models should include appropriate validations to prevent incomplete or inconsistent data.
  * Your models need *not* be totally comprehensive. Just the main product data will do.
2. Create a website that conforms to the following points:
  * Implement a front-end framework of your choice to provide a clean and usable UI.
    * The UI should look polished and be easy to use and navigate. It should handle user errors gracefully and provide informative messages when necessary.
    * BONUS POINTS: Make it [responsive](https://en.wikipedia.org/wiki/Responsive_web_design).
  * Implement appropriate views to enable the user to CRUD wine products.
  * Implement a view showing a paginated, searchable list that includes all wine products in the database. This view should:
    * Load one page at a time into the DOM. When navigating between pages, it should use AJAX to load the next page.
    * Display the current page number and total number of pages (e.g. "Page 2 of 7").
    * Present a search box at the top that will filter the list as the user types to include products in the database that match the search term. It should display no results until the user has entered at least 2 characters.
    * BONUS POINTS: Allow the user to also filter the product list by Varietal or Vineyard.
    * BONUS POINTS: Implement the product search using [Amazon CloudSearch](https://aws.amazon.com/cloudsearch).
  * Implement a view that allows the user to load data from the wine.com API. This view should:
    * Allow the user to specify how many products to load from the wine.com API (default should be 500).
    * Present a button that pulls in fresh data from the wine.com API. This should overwrite any existing wine.com data in our database.
    * Present a button that clears out the existing wine.com data (but leaves the user-submitted data intact).
    * When either button is pressed, present the user with a loading indicator until the operation is complete.
    * BONUS POINTS: Display a progress bar that reflects actual progress when loading data from the wine.com API.
3. Write some basic Rspec tests for your code.
