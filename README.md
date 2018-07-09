# Default Gradle Build File / Project Structure
Whenever I end up wanting to start a new side project, I end up trying to go through and figure out what the baseline I want to end up doing is and spend way too much time looking for the different Java libraries and setting up the build script in the way I want it.  This repository is going to hold my standard Gradle build for a non-Spring Boot application.

## Common Libraries Used
[Google GSON](https://github.com/google/gson) - Used for JSON serialization and de-serialization.  Chosen over Jackson as I think it has a bit more flexibility in how things are done if I need to mess with it.  And I like that I don't really have to annotate everything like you do with Jackson.
[Google Guava](https://github.com/google/guava) - Google's Java utilities.  I really should end up using these more than I do.  So to do so, I am putting this into the common package that I am going to end up using.
[JUnit](https://junit.org/junit5/) - My standard testing framework.  It's integrated into the Gradle Build and it's pretty much the industry standard.
[SLF4J](https://www.slf4j.org/) - I like to use this for the logging framework and point it to Log4J2.  I prefer this because I find it a bit easier to write the code that is done for the logging with this because of the ability to use {} and long parameter strings in logs.  This requires the Log4J2 SLF4J implementation as well.

## AWS Libraries Used
[Lambda Core & Events](https://github.com/aws/aws-lambda-java-libs) - The Amazon standard packages for writing AWS Lambda Functions which I am using as my default when I am not leveraging Spring Boot.
[AWS SDK 2.0]() - I am not running anything mission critical in side projects, and I prefer the more "modern" look of this, so this is my default AWS SDK.  If I were going to be using something mission critical, I would probably bounce back to the 1.x branch of the AWS SDK.

## To Research More
[Lambda Log4J2 Logging](https://github.com/aws/aws-lambda-java-libs/tree/master/aws-lambda-java-log4j2) - Need to research if this should be included in order to use Log4J2 throughout for everything.
