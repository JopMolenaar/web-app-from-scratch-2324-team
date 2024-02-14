# Travelmap

![Frame 15](https://github.com/JopMolenaar/WAFS-team-website/assets/47858242/48dab901-78e7-4c96-827f-83b9c4054a52)

## Description

This webapp makes you able to compare our visited and bucketlist countries in a nice colorfull interactive worldmap. When you click on a country that has a color, it opens a sidebar with content about the country and information about who has been there and who wants to go there. 
You can zoom in and scroll on the worldmap to see the countries better.

## Table of contents

- Installation
- If you want the backend too
- Use of features
- External data source properties
- Whishlist
- License

## Installation

1. Clone the repository:

    ```
    git clone https://github.com/JopMolenaar/web-app-from-scratch-2324-team.git
    ```

2. Open the cloned file with your code editor and start coding!

## Use of features

- Compare our visited and bucketlist countries in a nice colorfull interactive worldmap by the use of the buttons on the right top side of the screen with our names in it. 

- A sidebar with content about the country and information about who has been there and who wants to go there. 

- You can zoom in and scroll on the worldmap to see the countries better.

## External data source properties

In this application, we use two external data sources to get information about the selected country.

We use the Wikipedia API for the description about a country and the RestCountries API for the rest of the data.

Wikipedia documentation: https://www.mediawiki.org/w/api.php?action=help
RestCountries documentation: https://restcountries.com/

### Using the wikipedia API
For the wikipedia API we need to make two calls. We first need to search for the article about the country with the following query:

```
https://en.wikipedia.org/w/api.php?action=opensearch&origin=*&format=json&search=${country}
```

We get the search results back, from which we just pick the first one for our next call for the found article:

```
https://en.wikipedia.org/w/api.php?action=query&origin=*&prop=extracts&exsentences=5&format=json&titles=${wikiTitle}
```

With `prop=extracts` we ask for a short description and with `exsensences=5` we limit the length to 5 sentences.

We object back which contains the HTML for the description.

### Using the RestCountries API

This API is very simple. With one query we can get all the data about a specific country.

```
https://restcountries.com/v3.1/name/${country}?fullText=true
```

### Combining results
For quicker fetching we use `Promise.all` to fetch both countries at the same time. After we get the data back we combine it in one simple object, with only the data we need.


## Whishlist

- [ ] Fixing the accessibility on our website (tabbing and )
- [ ] Add tooltip (a little popup with the country name that shows on a mouseover event on the country)
- [ ] Testing the UX of the website with people outside of the devlopment team
- [ ] Add more data from different people
- [ ] Give all the paths a dataset with the matching country. 

## License

My website is open-source and released under the [MIT License](LICENSE).

## Aknolegdments

- Eefje Snel [Eefje Snel](LICENSE).
- Joppe Koops 
- Lynn Wolters 
- Jop Molenaar

## Sources

All used images are from [unsplash](https://unsplash.com/)
