## How to install Robot Framework on your windows machine

Robot-framework is a test-automating tool which is based on Python language.
It is based on simple keyword-driven synthax. Everyone can start with this frameowrk, even without great developer experience.

Here is an example of the test written with Robot Framework:

        *** Test cases ***
        Valid Login
          Open Browser To Login Page
          Input Username    demo
          Input Password    mode
          Submit Credentials
          Welcome Page Should Be Open
          [Teardown]    Close Browser

Here will be described how to start automating your test-cases for web-pages using this mighty framework.

Sadly Robot Framework is still not working with Python 3.6.0 for web-page testing so first of all you need to install Python 2.7 and pip.

1. Install python from [here](https://www.python.org/downloads/). During installation also check the box to install python in PATH.

    ![](/images/Python_install.png)

2. Install an alternative tool for command line - [ConEmu](https://conemu.github.io/). It has more adaptive design and tabs!
3. Open ConEmu and print "python"

    ![](/images/conemu_python.png)

    If you see the following message:

        Python 2.7.13 (v2.7.13:a06454b1afa1, Dec 17 2016, 20:42:59) [MSC v.1500 32 bit (Intel)] on win32
        Type "help", "copyright", "credits" or "license" for more information.
        >>>

    it means that python was installed correctly.  

4. To exit from python console use "Ctrl+Z"
5. Python only started bundling pip with Python 2.7.9. If the latest Python was installed then it means, that pip is also aready in the package. It can be checked by typing:

        pip --version

    In response can be seen the version of pip and where it was installed:

        $ pip --version
        pip 9.0.1 from c:\python27\lib\site-packages (python 2.7)

6. After installing Python install Robot Framework:

        pip install robotframework

7. An then for testing web-pages install selenium library:

        pip install robotframework-selenium2library

8. Also install docutils for some reStructuredText markup language for test data

        pip install docutils

9. Download [geckodriver](https://github.com/mozilla/geckodriver/releases) and save it to the folder with test-cases.


[Home](https://illuminatt.github.io)
