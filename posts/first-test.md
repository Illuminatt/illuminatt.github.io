In this chapter will be described how to write the simpliest test with robotframework.

The file structure is pretty simple. There should be geckodriver, resource.robot and Test Suite Name.robot

- geckodriver is a driver for Firefox Browser
- resource.robot is a configuration file for context words and variables
- Test Suite Name.robot is the Test Suite itself.

Down below is an example of Simple Search with Bing. The meaning of the keywords will be further explained.

        *** Settings ***
        Documentation     A test case with a single test for search in Bing.
        ...               There can be some more document information.
        ...               With 3 dots more lines can be added to the documentation.
        Resource          resource.robot # Data where keywords and variables are stored

        *** Test Cases ***
        Simple Bing Search   # Name of the test-case. Will be seen also in the command line during the execution.
            Open Browser To Bing Page
            Bing Should Be Open
            Input Search    cats images # Input with specified variable
            Start search
            Wait Until Keyword Succeeds   20    1   Page Should Contain Element   b_header # wait until special id of the website comes
            Page with Cats Should Be Open # validate that the title of the web page is correct
            [Teardown]    Close Browser



[Home](https://illuminatt.github.io)
