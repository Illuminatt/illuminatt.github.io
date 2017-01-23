In this chapter will be described how to write the simpliest test with robotframework.

The file structure is pretty simple. There should be at least 3 files: geckodriver for starting test on Firefox, resource.robot for variabes and keywords and Test-Suite-Name.robot - the test suite itself.

- geckodriver is a driver for Firefox Browser
- resource.robot is a configuration file for context words and variables
- Test-Suite-Name.robot is the Test Suite itself.

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

Here is the ressource.robot file with variables and kontext words

        *** Settings ***
        Documentation     A resource file with reusable keywords and variables.
        ...
        ...               The system specific keywords created here form our own
        ...               domain specific language. They utilize keywords provided
        ...               by the imported Selenium2Library.
        Library           Selenium2Library

        *** Variables ***
        ${BROWSER}        Firefox
        ${DELAY}          0
        ${VALID USER}     demo
        ${VALID PASSWORD}    mode
        ${BING URL}      http://bing.com/
        ${TEXT}           Cats images

        *** Keywords ***
        Open Browser To Bing Page
            Open Browser    ${BING URL}    ${BROWSER}
            Maximize Browser Window
            Set Selenium Speed    ${DELAY}
            Bing Should Be Open

        Bing Should Be Open
            Title Should Be    Bing

        Start search
            Click Button    sb_form_go

        Input Search
            [Arguments]    ${username}
            Input Text    sb_form_q    ${username}

        Page with Cats Should Be Open
            Title Should Be   cats images - Bing

To start the test go to source folder and execute the robot test suite. In this case Test-Suite-Name.robot:

        robot Search_bing.robot

Following result is to be seen if the test-case run correctly.

        ==============================================================================
        Search bing :: A test case with a single test for search in Bing.
        ==============================================================================
        Simple Bing Search                                                    | PASS |
        ------------------------------------------------------------------------------
        Search bing :: A test case with a single test for search in Bing.     | PASS |
        1 critical test, 1 passed, 0 failed
        1 test total, 1 passed, 0 failed
        ==============================================================================
        Output:  E:\Projects\RobotFramwork\output.xml
        Log:     E:\Projects\RobotFramwork\log.html
        Report:  E:\Projects\RobotFramwork\report.html

Also output, report and log will be created. If the test-case fails a screenshot with the last step will be created in the test-case folder.

Typical example of the test-case report:

![](/images/report.png)

[Home](https://illuminatt.github.io)
