# Acceptance Tests

# Skeleton package to start Codeception tests
We want to show you how to build your own tests from scratch

## Installation guide
We use a setup for our local Chrome browser. This is important to develop things. You can also go a way with the offical selenium docker chrome container and TigerVLC zu connect you. But on our daily work we use this.

For a client with a Mac we setup this little step tutorial. For windows user its a better way to go with npm packages.

### Installation steps
**Configure codeception.yml**  
* Add Webdriver Url and Host
* Add PHPBrowser Url
* Add REST Url 

or use environment vars to make this run local. Please without the last "/".
```bash
export WEBDRIVER_URL="127.0.0.1" && export WEBSITE_URL="https://www.testurl.de"
```
Install Chromedriver to connect your Selenium server to your local browser. Can be that there is also a way to only use Chromedriver. But we do not know this so far ;)
```bash
brew install --cask chromedriver
```

Install a local Selenium server. It runs by default on port 4444
```bash
brew install selenium-server-standalone
```

### Create Test
```vendor/bin/codecept g:cest acceptance {DIR}/{TestName}```

### Startup Selenium Server
```selenium-server -port 4444```

 ###Run your tests.
 The parameter --steps will show you the steps on the terminal. --html will generate a HTML report and -vvv gives you better verbose information.
```bash
vendor/bin/codecept run acceptance --steps --html -vvv
```
### Run a single test cest
```bash
vendor/bin/codecept run acceptance Search --steps --html -vvv
```
### Run a specific test
```bash
vendor/bin/codecept run acceptance Search/SearchCest:autocompleteItemsMatchSearchWord --steps --html -vvv
```


### Credits for basic package 
[Testify Never Code Alone](https://testify.nevercodealone.de)
