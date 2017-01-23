In this chapter will be described how to write the simpliest test with robotframework.

File structure is pretty simple. There should be geckodriver, resource.robot and <Test Suite Name>.robot

- geckodriver is a driver for Firefox Browser
- resource.robot is a configuration file for context words and variables
- <Test Suite Name>.robot is the Test Suite itself.

Here is an example of Simple Search with Bing:

        *** Settings ***
        Documentation     A test case with a single test for search in Bing.
        ...               There can be some more document information.
        Resource          resource.robot

        *** Test Cases ***
        Simple Bing Search
            Open Browser To Bing Page
            Bing Should Be Open
            Input Search    cats images
            Start search
            Wait Until Keyword Succeeds   20    1   Page Should Contain Element   b_tween
            Page with Cats Should Be Open
            [Teardown]    Close Browser



[Home](https://illuminatt.github.io)
