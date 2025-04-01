# selenium-driver-set

```python
import requests
from selenium import webdriver

def getWebDriver(BrowserName):
    '''Support Browser List: "Chrome" "Firefox" "Internet-Explorer" "Edge" "Brave" '''
    BowserList = [
        "Chrome",
        "Firefox",
        "Internet-Explorer",
        "Edge",
        "Brave",
    ]
    if   BrowserName == BowserList[0]:
        # Google-Chrome Browser
        from selenium.webdriver.chrome.service import Service as ChromeService
        from webdriver_manager.chrome import ChromeDriverManager
        driver = webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
    elif BrowserName == BowserList[1]:
        # Firefox Browser
        from selenium.webdriver.firefox.service import Service as FirefoxService
        from webdriver_manager.firefox import GeckoDriverManager
        driver = webdriver.Firefox(service=FirefoxService(GeckoDriverManager().install()))
    elif BrowserName == BowserList[2]:
        # Internet-Explorer
        from selenium.webdriver.ie.service import Service as IEService
        from webdriver_manager.microsoft import IEDriverManager
        driver = webdriver.Ie(service=IEService(IEDriverManager().install()))
    elif BrowserName == BowserList[3]:
        # Edge Browser
        from selenium.webdriver.edge.service import Service as EdgeService
        from webdriver_manager.microsoft import EdgeChromiumDriverManager
        driver = webdriver.Edge(service=EdgeService(EdgeChromiumDriverManager().install()))
    elif BrowserName == BowserList[4]:
        # Brave Browser
        from selenium.webdriver.chrome.service import Service as BraveService
        from webdriver_manager.chrome import ChromeDriverManager
        from webdriver_manager.core.os_manager import ChromeType
        driver = webdriver.Chrome(service=BraveService(ChromeDriverManager(chrome_type=ChromeType.BRAVE).install()))
    return driver
```
fileName: getWebDriver.py


# Useage

```python
from getWebDriver import getWebDriver

driver = getWebDriver("Chrome")

...
```
