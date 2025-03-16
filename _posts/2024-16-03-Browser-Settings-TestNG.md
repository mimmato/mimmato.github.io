---
title: Setting up your browser settings using TestNG annotations
date: 2024-11-03 00:00:00 +0800
categories: [Learning, Good Practices]
tags: [testng, pom, annotations]     # TAG names should always be lowercase
---

The idea of this article is to introduce the reader to a practice of separating the TestNG framework annotations (excluding @Test) in a separate file when applying Page Object Model patterns while designing applications. 

Please refer to the [Page Object Model] article if you have not read it already.

To recap, the Page Object Model or POM for short, allows us to separate page elements from test scripts, thus allowing us to focus on the test cases. It makes test suites much easier to maintain and oraganize. 

Using TestNG annotations, we can:

    Run tests using @Test
    Specify methods to be run before each suite using @BeforeSuite
    Specify methods to be run after each suite using @AfterSuite
    Run methods before each test class using @BeforeClass
    Run methods after each test class using @AfterClass
    Execute methods before each test method using @BeforeMethod
    Execute methods after each test method using @AfterMethod
    Create data-driven tests using @DataProvider

We could just place each of those annotations in our test scripts, however, a much more efficient way to manage and maintain our suite would be to have some of those annotations specified in a separate file and use inheritance in our test scripts and classes.

If we are to draw a tree chart for the TestNG annotations then we can see a clear coleration and have them paired according to function:

```less
@BeforeSuite
│
├── @BeforeTest
│   │
│   ├── @BeforeClass
│   │   │
│   │   ├── @BeforeMethod
│   │   │   │
│   │   │   ├── TEST
│   │   │   │
│   │   │   └── @AfterMethod
│   │   │
│   │   └── @AfterClass
│   │
│   └── @AfterTest
│
└── @AfterSuite
```


