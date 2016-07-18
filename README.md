# Binoculars

Binoculars is an open source tool for automating visual regression tests for web and mobile. Thanks to its simple API, Binoculars can be seamlessly integrated into your existing Selenium tests.

###Features
- Uses Selenium WebDriver API. Can be easily integrated into existing Selenium tests
- Support all browsers and mobile devices which include screenshot capability
- Uses Resemble.js Java implementation for sophisticated image comparisons algorithm (not pixel by pixel)
- Fully configurable - Each tiny configuration can be modified using Configuration API
- Detailed reports of visual mismatch

##How it Works

On its first run, Binoculars saves a baseline screenshot for all elements that need to be visually tested. Consecutive runs will capture a new screenshot for each element and compare it with the corresponding baseline.
Using its image comparison engine, Binoculars will check for mismatch in screenshots and fail the test if mismatch occurs.

##Getting Started

To initialize Binoculars, you must provide it with a WebDriver object.

``` java
WebDriver driver = new FirefoxDriver();
binoculars = new Binoculars(driver);
```

Binoculars is now ready to go! 

Next step would be start capturing elements in UI. Binoculars will locate elements on screen using WebDriver's By selectors. Each captured element is uniquely identified by its given label. 

In below example, we will capture logo image using ID selector type. We will label this element as "logo", so Binoculars can refer to it in the future.

``` java
binoculars.capture("logo", By.id("uh-logo"));
```

In order to check for regression in a specific element, you can compare an element with its baseline using label:

``` java
binoculars.compare("logo");
```

In order to check all captured elements in a test, you can compare all elements at once:

``` java
binoculars.compareAll();
```

##Configuration
Binoculars is fully configurable.
