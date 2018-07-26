# Default Gradle Build File / Project Structure
Whenever I end up wanting to start a new side project, I end up trying to go through and figure out what the baseline I want to end up doing is and spend way too much time looking for the different Java libraries and setting up the build script in the way I want it.  This repository is going to hold my standard Gradle build for a non-Spring Boot application.

## Common Libraries Used
* [Google GSON](https://github.com/google/gson) - Used for JSON serialization and de-serialization.  Chosen over Jackson as I think it has a bit more flexibility in how things are done if I need to mess with it.  And I like that I don't really have to annotate everything like you do with Jackson.
* [Google Guava](https://github.com/google/guava) - Google's Java utilities.  I really should end up using these more than I do.  So to do so, I am putting this into the common package that I am going to end up using.
* [JUnit](https://junit.org/junit5/) - My standard testing framework.  It's integrated into the Gradle Build and it's pretty much the industry standard.
* [Log4J2](https://logging.apache.org/log4j/2.x/) - Reading more, I discovered there is no real need to have the SLF4J stuff in front of Log4J2, so I am removing that requirement and just pointing directly to it.  Especially because in my side projects I don't need a logging facade to switch out implementations and if really needed, I can do that with Log4J2 anyways.

## AWS Libraries Used
* [Lambda Core & Events](https://github.com/aws/aws-lambda-java-libs) - The Amazon standard packages for writing AWS Lambda Functions which I am using as my default when I am not leveraging Spring Boot.
* [Lambda Log4J2 Logging](https://github.com/aws/aws-lambda-java-libs/tree/master/aws-lambda-java-log4j2) - Set up as the main logging mechanism for all Lambda services I am writing, which are my defaults for side projects now.
* [AWS SDK 2.0]() - I am not running anything mission critical in side projects, and I prefer the more "modern" look of this, so this is my default AWS SDK.  If I were going to be using something mission critical, I would probably bounce back to the 1.x branch of the AWS SDK.