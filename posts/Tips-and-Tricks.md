Here are some tips about for successfull creating test-cases with robotframework

1. First of all create a test-suite using natual language. All the keywords can be translated and interpreted later in _resource.robot_
2. To implement waits on the website use the following construction:
        Wait Until Keyword Succeeds   20    1   Page Should Contain Element   b_header

    where _b_header_ is the id of the page, which you are waiting for

![Id can be found by using developer tools in Chrome or Firefox](/images/devtools-id.png)

    and "20" is 20 second of timeout
    "1" means that robotframework will check every second if the id has appeared on the website

[Home](https://illuminatt.github.io)
