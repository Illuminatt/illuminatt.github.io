Here are some tips about for successfull creating test-cases with Robot Framework.

1. First of all create a test-suite using natual language. All the keywords can be translated and interpreted later in _resource.robot_.
2. To implement waits on the website use the following construction:

        Wait Until Keyword Succeeds   20    1   Page Should Contain Element   b_header

    where _b_header_ is the id of the page, which you are waiting for. The ID can be found with developer Tools for Chrome or Firefox or in every other browser.

![](/images/devtools-id.png)

"20" is 20 seconds of timeout  
"1" means that Robot Framework will check every second if the ID has appeared on the website

[Home](https://illuminatt.github.io)
