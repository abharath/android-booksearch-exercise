# Book Search App

Android app that leverages the [OpenLibrary API](https://openlibrary.org/developers/api) to search books and display cover images.

![Imgur](http://i.imgur.com/x9gZ2cH.gif)

## Overview

The app does the following:

1. Fetch the books from the [OpenLibrary Search API](https://openlibrary.org/dev/docs/api/search) in JSON format
2. Deserialize the JSON data for each of the books into `Book` objects
3. Build an array of `Book` objects and create an `ArrayAdapter` for those books
4. Define `getView` to define how to inflate a layout for each book row and display each book's data.
5. Attach the adapter for the books to a ListView to display the data on screen
6. Use SearchView to search for books with a title
7. Show ProgressBar before each network request
8. Add a detail view to display more information about the selected book from the list
9. Use a share intent to recommend a book to friends

To achieve this, there are four different components in this app:

1. `BookClient` - Responsible for executing the API requests and retrieving the JSON
2. `Book` - Model object responsible for encapsulating the attributes for each individual book
3. `BookAdapter` - Responsible for mapping each `Book` to a particular view layout
4. `BookListActivity` - Responsible for fetching and deserializing the data and configuring the adapter

## Libraries

This app leverages two third-party libraries:

 * [Android AsyncHTTPClient](http://loopj.com/android-async-http/) - For asynchronous network requests
 * [Picasso](http://square.github.io/picasso/) - For remote image loading
