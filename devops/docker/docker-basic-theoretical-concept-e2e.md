# Docker
## Requirement
If your goal is to ship the software application in the real world one of the most powerful concepts is to understand is containerization. When developing locally it solves the age-old problem it works on my machine and when deploying in the cloud it solves the age-old problem of this architecture doesn't scale.

## Computer
> Its a box that has three important component inside, a cpu for calculating things, random access memory ram for the application to you're using right now and a disk to store things you might use later
> This is a bare metal hardware but in order to use it we need an operating system
> Most importantly the OS provides a kernel that sit on top of bare metal allowing software applications to run on it
> In the olden days we use to go to store to buy software (physical media) to physcially install on the machine, but nowadays most software is delivered via the internet through the magic of networking
> When we are watching the youtube video our computer is called the client but you and billions other users are getting that data from remote computers called servers
> When an app starting reaching millions of people weird things begin to happen, the cpu becomes exhausted handling all the incoming request, Diskio slows down the network, bandwidth get maxed out and the database becomes too large to query effectively on top of that you wrote some garbage code that's causing race conditions, memory leaks and unhandled errors that will eventually grind your server to a halt, the big question is how do we scale  our infrastructure
> A server can scale up in two ways: vertically or horizontally
> To scale vertically you take your one server and increase its ram and cpu, this can take you pretty far but eventually you hit a ceiling, the other option is to scale horizontally where you distribute your code to multiple smaller servers which are often broken down into microservices that can run and scale independently but distributed systems like this aren't practical when talking about bare metal because the actual resource allocation varies one way engineers address this is with virtual machines using tools like hypervisor
> Hypervisor can isolate and run multiple OS on a single machine that helps, but a vm's allocation of cpu and memory is still fixed and that where docker comes in

## Docker
>The application running on top of the docker engine all share the same host OS kernel and use resources dynamically based on their need.
>Under the hoods docker's running a  daemon or persistent process that makes all this  magic possible and gives us OS level virtualization
>What's awesome is that any developer can easily harness this power by simply installing Docker desktop, It allows you to develop software without having to make massive changes to your local system but here's how Docker works in three easy step
>> First you start with a Dockerfile, this is like a blueprint that tells docker how to configure the environment that runs your application
>> The Dockerfile is then use to build an image which contains an OS, our dependencies and our code, like a template for running your application and we can upload this image to the cloud to places like Dockerhub and share it with the world but an image by itself doesn't do anything, we need to run it as a container which itself is an isolated package running our code that int heory could scale infinitely in the cloud
>> Containers are stateless which means when they shut down all the data inside them is lost but that makes them portable and they can run on every major cloud platform without vendor lock in pretty cool but the best way to learn Docker is to actually run a  container
>
>Lets create a Dockerfile, A dockerfile contains a collection of instructions which by convention are in all caps from is usually the first instruction you'll see which points to a base image to get started this will foten be a Linux distro and may be followed by a colon which is an optional image tag and in this case sepcifies the version of OS next we have the 