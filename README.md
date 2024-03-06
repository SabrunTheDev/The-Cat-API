# The Cat App

# R-ALAB 308A.4.1

## Description

The provided code is a JavaScript implementation that interacts with the Cat API to fetch information about cat breeds and display relevant details and images. Below is an overview of the key components and functionalities:

## 1. Initialization

- The code begins with importing necessary modules: `Carousel` and `axios`.
- DOM elements such as `breedSelect`, `infoDump`, `progressBar`, `getFavouritesBtn`, and `carousel` are identified for later use.

## 2. Initial Load Function

- An asynchronous function named `initialLoad` fetches a list of cat breeds from the Cat API using the `fetch` API.
- The retrieved breeds are then used to dynamically populate the breed selection dropdown (`breedSelect`) with options.

## 3. Event Listener for Breed Selection

- An event listener is set up for the `breedSelect` element to trigger when a user selects a breed.
- Upon selection, it fetches detailed information about the chosen breed, including images.
- The received data is then used to update the carousel and information section (`infoDump`) accordingly.

```javascript
breedSelect.addEventListener("change", async (retrieveInfo) => {
  breedSelect.style.cursor = "wait";
  const breedInfomationId = breedSelect.value;
  // ...
});
```

## 4. Carousel Rendering

- The carousel is dynamically rendered with images of the selected breed.
- Information about the breed, such as name, description, origin, temperament, and a Wikipedia link, is displayed in the `infoDump` section.

```javascript
catInfo.forEach((breed) => {
  const breedOption = document.createElement("OPTION");
  breedOption.value = breed.id;
  breedOption.textContent = breed.name;
  breedSelect.appendChild(breedOption);

  const breedImagesDiv = document.createElement("div");
  // ...
  carousel.appendChild(breedImagesDiv);
});

start();
```
