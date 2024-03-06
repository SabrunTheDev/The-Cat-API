# The Cat App

# R-ALAB 308A.4.1

## Description

The provided code is a JavaScript implementation that interacts with the Cat API to fetch information about cat breeds and display relevant details and images. Below is an overview of the key components and functionalities:

### [CodeSandbox - JavaScript Axios Lab](https://codesandbox.io/p/sandbox/ajax-fetch-and-axios-lab-template-forked-ms8tw9?layout=%257B%2522sidebarPanel%2522%253A%2522EXPLORER%2522%252C%2522rootPanelGroup%2522%253A%257B%2522direction%2522%253A%2522horizontal%2522%252C%2522contentType%2522%253A%2522UNKNOWN%2522%252C%2522type%2522%253A%2522PANEL_GROUP%2522%252C%2522id%2522%253A%2522ROOT_LAYOUT%2522%252C%2522panels%2522%253A%255B%257B%2522type%2522%253A%2522PANEL_GROUP%2522%252C%2522contentType%2522%253A%2522UNKNOWN%2522%252C%2522direction%2522%253A%2522vertical%2522%252C%2522id%2522%253A%2522cltat1nh00006357827u0k1li%2522%252C%2522sizes%2522%253A%255B70%252C30%255D%252C%2522panels%2522%253A%255B%257B%2522type%2522%253A%2522PANEL_GROUP%2522%252C%2522contentType%2522%253A%2522EDITOR%2522%252C%2522direction%2522%253A%2522horizontal%2522%252C%2522id%2522%253A%2522EDITOR%2522%252C%2522panels%2522%253A%255B%257B%2522type%2522%253A%2522PANEL%2522%252C%2522contentType%2522%253A%2522EDITOR%2522%252C%2522id%2522%253A%2522cltat1nh0000235780g68mtiw%2522%257D%255D%257D%252C%257B%2522type%2522%253A%2522PANEL_GROUP%2522%252C%2522contentType%2522%253A%2522SHELLS%2522%252C%2522direction%2522%253A%2522horizontal%2522%252C%2522id%2522%253A%2522SHELLS%2522%252C%2522panels%2522%253A%255B%257B%2522type%2522%253A%2522PANEL%2522%252C%2522contentType%2522%253A%2522SHELLS%2522%252C%2522id%2522%253A%2522cltat1nh00003357873dxavk8%2522%257D%255D%252C%2522sizes%2522%253A%255B100%255D%257D%255D%257D%252C%257B%2522type%2522%253A%2522PANEL_GROUP%2522%252C%2522contentType%2522%253A%2522DEVTOOLS%2522%252C%2522direction%2522%253A%2522vertical%2522%252C%2522id%2522%253A%2522DEVTOOLS%2522%252C%2522panels%2522%253A%255B%257B%2522type%2522%253A%2522PANEL%2522%252C%2522contentType%2522%253A%2522DEVTOOLS%2522%252C%2522id%2522%253A%2522cltat1nh000053578rrvmffpe%2522%257D%255D%252C%2522sizes%2522%253A%255B100%255D%257D%255D%252C%2522sizes%2522%253A%255B59.61798570799088%252C40.38201429200912%255D%257D%252C%2522tabbedPanels%2522%253A%257B%2522cltat1nh0000235780g68mtiw%2522%253A%257B%2522id%2522%253A%2522cltat1nh0000235780g68mtiw%2522%252C%2522tabs%2522%253A%255B%255D%257D%252C%2522cltat1nh000053578rrvmffpe%2522%253A%257B%2522tabs%2522%253A%255B%257B%2522id%2522%253A%2522cltat1nh000043578t3k09e4q%2522%252C%2522mode%2522%253A%2522permanent%2522%252C%2522type%2522%253A%2522UNASSIGNED_PORT%2522%252C%2522port%2522%253A0%252C%2522path%2522%253A%2522%252F%2522%257D%255D%252C%2522id%2522%253A%2522cltat1nh000053578rrvmffpe%2522%252C%2522activeTabId%2522%253A%2522cltat1nh000043578t3k09e4q%2522%257D%252C%2522cltat1nh00003357873dxavk8%2522%253A%257B%2522tabs%2522%253A%255B%255D%252C%2522id%2522%253A%2522cltat1nh00003357873dxavk8%2522%257D%257D%252C%2522showDevtools%2522%253Atrue%252C%2522showShells%2522%253Atrue%252C%2522showSidebar%2522%253Atrue%252C%2522sidebarPanelSize%2522%253A15%257D)

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
