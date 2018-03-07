# Changelog
This project versioning adheres to [Semantic Versioning](http://semver.org/).

## Unreleased
### Added
- Added `getCapabilities()` method of `RemoteWebDriver`, to retrieve actual capabilities acknowledged by the remote driver on startup.
- Added option to pass required capabilities when creating `RemoteWebDriver`. (So far only desired capabilities were supported.)
- Added new expected conditions:
    - `titleMatches` - current page title matches regular expression
    - `elementTextIs` - text in element exactly equals given text
    - `elementTextMatches` - text in element matches regular expression
    - `elementTextContains` (as an alias for `textToBePresentInElement`) - text in element contains given text
    - `numberOfWindowsToBe` - number of opened windows equals given number

### Changed
- `Symfony\Process` is used to start local WebDriver processes (when browsers are run directly, without Selenium server) to workaround some PHP bugs and improve portability.
- Clarified meaning of selenium server URL variable in methods of `RemoteWebDriver` class.
- Deprecated `setSessionID()` and `setCommandExecutor()` methods of `RemoteWebDriver` class; these values should be immutable and thus passed only via constructor.
- Deprecated `WebDriverExpectedCondition::textToBePresentInElement()` in favor of `elementTextContains()`

## 1.2.0 - 2016-10-14
- Added initial support of remote Microsoft Edge browser (but starting local EdgeDriver is still not supported).
- Utilize late static binding to make eg. `WebDriverBy` and `DesiredCapabilities` classes easily extensible.
- PHP version at least 5.5 is required.
- Fixed incompatibility with Appium, caused by redundant params present in requests to Selenium server.

## 1.1.3 - 2016-08-10
- Fixed FirefoxProfile to support installation of extensions with custom namespace prefix in their manifest file.
- Comply codestyle with [PSR-2](http://www.php-fig.org/psr/psr-2/).

## 1.1.2 - 2016-06-04
- Added ext-curl to composer.json.
- Added CHANGELOG.md.
- Added CONTRIBUTING.md with information and rules for contributors.

## 1.1.1 - 2015-12-31
- Fixed strict standards error in `ChromeDriver`.
- Added unit tests for `WebDriverCommand` and `DesiredCapabilities`.
- Fixed retrieving temporary path name in `FirefoxDriver` when `open_basedir` restriction is in effect.

## 1.1.0 - 2015-12-08
- FirefoxProfile improved - added possibility to set RDF file and to add datas for extensions.
- Fixed setting 0 second timeout of `WebDriverWait`.
