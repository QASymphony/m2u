#m2u 
JMeter JTL to JUnit test results converter.

This project aims to ease conversion from JMeter JTL format to JUnit-compatible XML. This is due to some continuous 
integration systems (namely Hudson/Jenkins) support only a subset of JTL spec and/or take a very opinionated way of
displaying the results, which makes them unusable if JMeter is used for functional testing.

Currently only these JMeter JTL elements are supported:

* `<sample/>`
* `<httpSample/>`

### Following these steps below to build this jar and how to use it

## Reprequisite environment ?
- Install [apache maven](https://maven.apache.org/download.cgi) in your PC.
- Configure maven path in with Environment variables
- Download all source code here and put it in your PC.

## How to build it?
In order to build this jar, just run maven without any arguments:

    $ mvn


## How to use it?
Copy m2u.jar in the output folder to a place which you have jtl file and execute command:

    java -jar m2u.jar --input <jmeter.jtl> --output <junit.xml> [--testSuiteName <name of the test suite>]

If the `<name of the test suite>` argument is not given, it will default to `jmeter`.

## How to configure as task in Bamboo / Jenkins tool ?

In Bamboo tool:
1. Copy m2u.jar file into your automation project under Bamboo build directory
2. Add new task as SCRIPT in Default Job of the Configuration build projects
![Bamboo Task](/images/bamboo_task.png?raw=true)

In Jenkins tool:
1. Copy m2u.jar file into your automation project under Jenkins job
2. Add build step with Execute Shell in the configuration of Jenkins job.
![Jenkins Build](/images/jenkins_task.png?raw=true)

## License
This software is available under GNU GPL license. Please see file `LICENSE` for details.
