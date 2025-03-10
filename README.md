# Quote-Generator #

The Quote Generator is a simple web application that fetches random quotes from an external API and displays them along with their authors. It features a clean and user-friendly interface, allowing users to get a new quote with the click of a button.

## Features

* **Random quotes:** Fetches and displays random quotes from an external API
* **Interactive button:** Allows users to fetch a new quote each time the "Get Quote" button is clicked
* **Responsive UI:** Styled with modern CSS to provide a clean and appealing design
* **Real-time data:** Fetches and displays quotes instantly using JavaScript and external API

## Technologies used

* **HTML:** The structure and layout of the Quote Generator app
* **CSS:** Styling to enhance the design and user experience
* **JavaScript:** Fetches random quotes using the ```fetch()``` method from an API and updates the displayed content dynamically

## How to use

1. **Get a quote:**
   * Open the app in your browser
   * A random quote and its author will be displayed on the page
   * To get a new quote, click the "Get quote" button
2. **UI Components**
   * **Quote text:** Displays the random quote
   * **Author name:** Displays the name of the author of the quote
   * **Get quote button:** Click this button to fetch a new random quote

## Code explanation
**HTML**
The HTML file defines the structure of the application:
  * A header with the title of the app "Quote Generator"
  * A section to display the quote and the author's name
  * A button to fetch new quotes
  ```HTML
  <div class="wrapper">
      <h1>Quote generator</h1>
      <div class="container">
          <div class="display">
              <p id="quote">Lorem ipsum dolor sit amet consectetur adipisicing elit...</p>
              <h3 id="author">Lorem</h3>
          </div>
          <button id="btn">Get Quote</button>
      </div>
  </div>
  ```
**CSS**
The CSS file provides styling for the Quote generator:
  * Centered layout for a clean and modern look
  * Styling for the quote text, author name and button
  * Responsive design to adjust for different screen sizes
  ```CSS
  body {
    background-color: #67729D;
  }

  .wrapper {
    width: 400px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  ```

**JavaScript**
The JavaScript file handles fetching random quotes from the API:
  * It makes a ```GET``` REQUEST TO THE ```https://api.quotable.io/random``` api
  * It then updates the displayed quote and author when the data is received

  ```JavaScript
  const url = "https://api.quotable.io/random";
  
  let getQuote = () => {
      fetch(url)
      .then((data) => data.json())
      .then((item) => {
          quote.innerText = item.content;
          author.innerText = item.author;
      });
  };
  
  window.addEventListener("load", getQuote);
  btn.addEventListener("click", getQuote);
  ```
