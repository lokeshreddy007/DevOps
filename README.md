# Devpos Quick Reference

##### Jenkins #####

`Jenkins - Build great things at any scale` 
1. The leading open source automation server.
2. To build and test software project continously
3. It has number of plugin which is the heart of Jenkins
4. Setup Jenkins to watch for any changes in repositories like for example you are SVN or github and Automatically to a build with tools like Ant  and Maven and utilise the container Technologies docker and kubernetes,initiate test take actions like a rolling back or rolling forward.For more refer here [jenkins](https://jenkins.io)

##### Continuous Integration #####

`Continuous Integration` is practised in which developer required to commit changes to the source code in the shared repository several times a day or more frequently than used to and as might know Jenkins is a continuous integration tool which enable the developers to commit changes in the shared repository several times and commit made in the repository is built,and it give the result so that it allows to detect the problems early

##### Jenkins Architecture #####

```cpp

                         ____________ Slave
                        |                
Git --Jenkins Master----|
                        |____________ Slave

```

`It is a Distributed architecture.`
`Master` can have multiple slave

###### Master ######

1. Scheduling jobs
2. Communicating with the slaves
3. Monitor the slaves
4. Present the results
5. Master can also execute build jobs

###### Slave ######

1. Communicating with Jenkins Master
2. Can run in different OS
3. Execute jobs
4. Flexibility

###### Freestyle project ######

1. This is the central feature of Jenkins. 
2. Jenkins will build your project, combining any SCM with any build system, and this can be even used for something other than software build.

` Create Freestyle project with [ForJenkisExample](https://github.com/lokeshreddy007/ForJenkisExample) `
Create a project then select Freestyle project. Next Configure page shows up then in Source Code Management select git and give repository link. In Build select execute shell then add below two line

```java

javac helloworld.java
java HelloWorld

```
After then click on build now. After Build complete to see output click on console output

###### Scheduling Jobs ######

Use `CRON` expressions to schedule job

    * It is suitable for repetitive task 
    * To allow periodically scheduled tasks to produce even load on the system, the symbol H (for “hash”) should be used wherever possible. 
    * This field follows the syntax of cron (with minor differences). Specifically, each line consists of 5 fields separated by TAB or whitespace:
        * MINUTE HOUR DOM MONTH DOW
        * MINUTE	Minutes within the hour (0–59)
        * HOUR	The hour of the day (0–23)
        * DOM	The day of the month (1–31)
        * MONTH	The month (1–12)
        * DOW	The day of the week (0–7) where 0 and 7 are Sunday.
    * In addition, @yearly, @annually, @monthly, @weekly, @daily, @midnight, and @hourly are supported as convenient aliases. These use the hash system for automatic balancing. 
    
###### Examples ######

```cpp

// every fifteen minutes (perhaps at :07, :22, :37, :52)
H/15 * * * *
// every ten minutes in the first half of every hour (three times, perhaps at :04, :14, :24)
H(0-29)/10 * * * *
// once every two hours at 45 minutes past the hour starting at 9:45 AM and finishing at 3:45 PM every weekday.
45 9-16/2 * * 1-5
// once in every two hours slot between 9 AM and 5 PM every weekday (perhaps at 10:38 AM, 12:38 PM, 2:38 PM, 4:38 PM)
H H(9-16)/2 * * 1-5
// once a day on the 1st and 15th of every month except December
H H 1,15 1-11 *

```
