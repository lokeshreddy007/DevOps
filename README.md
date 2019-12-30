# Devpos Quick Reference

##### Jenkins #####

`Jenkins - Build great things at any scale` 
1. The leading open source automation server.
2. To build and test software project continously
3. It has number of plugin which is the heart of Jenkins
4. Setup Jenkins to watch for any changes in repositories like for example you are SVN or github and Automatically to a build with tools like Ant  and Maven and utilise the container Technologies docker and kubernetes,initiate test take actions like a rolling back or rolling forward.For more refer here (jenkins)[https://jenkins.io]

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
