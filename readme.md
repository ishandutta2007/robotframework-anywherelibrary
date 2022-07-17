# [AnywhereLibrary for robotframework](https://github.com/luisxiaomai/robotframework-anywherelibrary)
[![PyPI version](https://badge.fury.io/py/robotframework-anywherelibrary.svg)](https://badge.fury.io/py/robotframework-anywherelibrary) 
[![Build status](https://travis-ci.org/luisxiaomai/robotframework-anywherelibrary.svg?branch=master)](https://travis-ci.org/luisxiaomai/robotframework-anywherelibrary)
[![codecov](https://codecov.io/gh/luisxiaomai/robotframework-anywherelibrary/branch/master/graph/badge.svg)](https://codecov.io/gh/luisxiaomai/robotframework-anywherelibrary)
[![Join the chat at https://gitter.im/anywherelibrary/Lobby](https://badges.gitter.im/anywherelibrary/Lobby.svg)](https://gitter.im/anywherelibrary/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![GitHub license](https://img.shields.io/badge/license-ApacheLicense2.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)
## Introduction

AnywhereLibrary is a cross platform (desktop browser, Android, iOS) testing library for Robot Framework that leverages the [Selenium 2 (WebDriver)](<http://seleniumhq.org/docs/03_webdriver.html/>) libraries internally to control a web browser and [Appium](<http://appium.io/>) as mobile test automation framework for use with native and hybrid apps. 

This library is especially suitable for handling [SPA (single-page apps)](http://en.wikipedia.org/wiki/Single-page_application) with responsive design patterns. With this you only need to generate a set of scripts to cover all platforms (desktop browser, Android, iOS). 

On the other hand, not any UI test automation framework is made for your real business. If this library isn't suitable for your business, it's highly recommended that you fork this repository as a prototype for UI test automation. Customize your own AnywhereLibrary in accordance to your actual business requirements.

## Installation

```bash	
python3 setup.py install
```
## Directory Layout

#### doc/
> Keyword documentation.
    
#### sample-code/
> A sample test case which can run in desktop browser, sample Android and iOS webview apps with different platform parameter inputs.

#### src/base
> Python source code.
    
#### src/cfg
> Configuration file which stores all parameters for initializing the driver.

## Usage

To write tests with Robot Framework and AnywhereLibrary, AnywhereLibrary must be imported into your RF test suite. See [Robot Framework User Guide](https://code.google.com/p/robotframework/wiki/UserGuide) for more information.

As it uses Appium for its mobile solution, please make sure your Appium server is up and running. For how to use Appium, please refer to the [Appium Documentation](http://appium.io/getting-started.html).

##### Before Running the Test Case
You must use the *`Initial Driver`* keyword with platform value as the parameter input; after the test case you must use *`Tear Down Driver`* keyword to tear down the related driver. Also you need to do some modifications in *`configuration.xml`* file in *`/AnywhereLibrary/cfg`*.

##### Locating elements

All keywords in AnywhereLibrary that need to find an element on the page take an argument, `locator`. AnywhereLibrary supports a subset of the WebDriver locator strategies. Currently available locator strategies are:

    find by "class" (i.e., ui component type)
    find by "xpath" (i.e., an abstract representation of a path to an element, with certain constraints)

Supported strategies are:

| *Strategy* | *Example*                                  | *Description*                                |
| ---------- | ------------------------------------------ | -------------------------------------------- |
| xpath      | `Click`  | `//div[@id='my_element']`       | Matches with arbitrary XPath expression      |
| xpath      | `Click`  | `xpath=//div[@id='my_element']` | Matches with arbitrary XPath expression      |
| class      | `Click`  | `class=android.widget.Button`   | Matches another element by their class name  |
| ...        | Coming soon...  | Coming soon...           |                                              |

## Running Sample Cases

```bash
pybot --variable platform:chrome webviewTest.txt
pybot --variable platform:firefox webviewTest.txt
pybot --variable platform:iphone webviewTest.txt
```
## Documentation

Keywords at a Glance:

- `Initial Driver`
- `Tear Down Driver`
- `Click`
- `Type`
- `Element Find`
- `Get Text`
- `Get Value`
- `Verify Text`
- `Verify Value`
- `Is Element Present`
- `Page Should Contain Element`
- `Page Should Not Contains Element`
- `Wait For Element Present`
- `Wait No Such Element Present`
- `Switch To Native`
- `Switch To Webview`
- `Capture Page Screenshot`
- `Execute Javascript`

* mobile gestures
  - Coming Soon...

More details about keyword documentation could be found at [Keyword Documentation](http://luisxiaomai.github.io/robotframework-anywherelibrary/doc/AnywhereLibraryDocument.html)

## Plan

* Add more keywords.

## FAQ

TODO

## License

* [MIT](https://opensource.org/licenses/MIT)
