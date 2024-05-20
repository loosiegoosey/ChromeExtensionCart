## Overview

Overview

The Chrome Extension Cart is a browser extension designed to simplify online shopping. It automates the process of adding items to an online shopping cart across various e-commerce websites. By using this extension, users can streamline their shopping experience, saving time and effort.

##
## Features

Features

- **Automated Cart Insertion**: Automatically adds selected items to the shopping cart on various e-commerce platforms.
- **Domain Extraction**: Extracts and processes domain information from URLs.
- **Seamless Integration with Chrome**: Easily integrates with Chrome browser for a smooth user experience.

##
## Installation Instructions

Installation Instructions

1. **Clone the Repository**: 
    ```sh
    git clone https://github.com/sullyo/ChromeExtensionCart.git
    ```
2. **Navigate to the Extension Directory**:
    ```sh
    cd path/to/ChromeExtensionCart
    ```
3. **Load the Extension in Chrome**:
    - Open Chrome and go to `chrome://extensions/`.
    - Enable "Developer mode" by toggling the switch in the upper-right corner.
    - Click on the "Load unpacked" button.
    - Select the directory where you cloned the repository.

4. **Verify Installation**:
    - The extension should now appear in your extensions list. Ensure it is enabled.

##
## Usage Examples

Usage Examples

1. **Adding Items to Cart**:
    - After installing the extension, navigate to any supported e-commerce website.
    - Click on the extension icon in the Chrome toolbar.
    - Click the "Add to Cart" button in the popup. This will trigger the script to automate the cart addition process.

```javascript
// In popup.js
document.getElementById('clickme').addEventListener('click', AddToCart);

function AddToCart() {
 chrome.tabs.executeScript(null, { file: "jquery.js" }, function() {
    chrome.tabs.executeScript(null, { file: "autoCart.js" });
});
}
```

##
## Code Summary

Code Summary

The project consists of the following key files:

- **autoCart.js**: Contains the main functionality for extracting domain information and processing the shopping cart data.
  ```javascript
  function extractDomain(url) {
      var domain;
      if (url.indexOf("://") > -1) {
          domain = url.split('/')[2];
      } else {
          domain = url.split('/')[0];
      }
      domain = domain.split(':')[0];
      return domain;
  }

  function finish(data){
    xmlDoc = $.parseXML( xmlString ),
    $xml = $( xmlDoc ),
    Id = $xml.find( 'id' );
    size = $xml.find('title');
    productNumber = new Array();
  }
  ```

- **jquery.js**: A local copy of jQuery to be used within the extension's context.
- **popup.js**: Handles interaction with the browser's popup interface and injects the necessary scripts into the current tab.
  ```javascript
  function AddToCart() {
   chrome.tabs.executeScript(null, { file: "jquery.js" }, function() {
      chrome.tabs.executeScript(null, { file: "autoCart.js" });
  });
  }

  document.getElementById('clickme').addEventListener('click', AddToCart);
  ```

- **tempstore.js**: An additional script file for handling domain extraction and processing XML data.
  ```javascript
  function extractDomain(url) {
      var domain;
      if (url.indexOf("://") > -1) {
          domain = url.split('/')[2];
      } else {
          domain = url.split('/')[0];
      }
      domain = domain.split(':')[0];
      return domain;
  }

  function finish(data){
    xmlDoc = $.parseXML( xmlString ),
    $xml = $( xmlDoc ),
    Id = $xml.find( 'id' );
    size = $xml.find('title');
    productNumber = new Array();
  }
  ```
  
##
## License

License

This project is licensed under the MIT License. See the LICENSE file for more details.