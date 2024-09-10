## Brief Introduction About Yourself

college and work experience and technoligies work on

## Scenario Based Question

## Consider a company build a monolithic architecture that handles a lot of product, now company is expanding, then monlithic architecure started causing problem, how do you think that company should shift from monolithic to microservices and how do they deploy there containers and how do they implement kubernetes in it, how can they club kubernetes in it

Describe about microservices what it is
Key Differences
Feature                monolithic                                   Microservices

                    High internal complexity                    Lower internal complexity
Complexity          Simpler deployment                          More complex deployment


Scalability         Scales as a single unit,                    Individual components can be scaled
                    which can be less efficient                 independently


Deployment          Initally faster for small teams             Enables faster development cycles
                    But slows down as the app grows             after initial setup


Technology Stack    Typically limited to s single               Supports using different technology stack
                    technology stack                            for different services


Fault Isolation     A bug in any module can potentially         Better fault isolation
                    bring down the entire application           a bug in one service does not affect other


Data Management     Shared Database schema                      Each service can have its own database
                                                                and schema


Team Structure      Centralized team working on the             Enables small, cross-funcitonal teams
                    entire application                          focused on specific services


Operational         Lower operational complexity                Higher operational complexity
Overhead            but can be harder to scale                  requires more tools and processes


Consistency         Easier to manitain strong                   Requires strategies for eventual
                    consistency                                 consistency across services


Communication       Method calls within the                     Network calls between services,
                    same process                                requiring api gateways or
                                                                service mesh


Update Cycles       Updates affect the whole                    Services can be updated independently
                    application, requiring full                 reducing the scope of testing
                    regression tests


Reliaibility        A single point of failure                   Designed for resillence, with services
                                                                running independently


Resource            Uniform resource allocation, which          Tailored resource allocation based 
Utilization         may lead to inefficiency                    on service needs


Startup Time        Longer startup times as the                 Typically shorter startup times for
                    application grows                           individual services


## Can you explain the kubernetes architecture

 > It contains two component master node and worker node
    >> Master node
        >>> Control plane
        >>> api server
        >>> scheduler
        >>> etcd
    >> Worker node
        >>> kubelet
        >>> kubeproxy

## Why should i choose kubernetes and why shouldnt i go for docker swarm

 > Cluster autoscaler
 > Tools can be connected to kubernetes

## What are all services you have worked on kubernetes

 > 4 types of services
    >> Clusterip
    >> Nodeport
    >> LoadBalancer
        >>> Internal Loadbalancer - The distribution is done for pod
        >>> External Loadbalancer - It direct the external traffic to the pod
    >> External Name

## Consider your company, your technical manager want to optimise the workload, you are on legacy system, how can i use kubernetes over here

 > 

## Consider you are a working in quick ride company and you are a devops in sre team, they want to increase the servers and how do u think that you will deal with the servers and kubernetes will be helpful over here

 > You can see the metrics how to the services are behaving and we can increase the nodes in kubernetes template of autoscaling group

## Both prometheus and grafana are clubbed together or separate entity


## What do you understand by namespaces in kubernetes

 > 

## What is the purpose of operator in kubernetes

 > 

## What are the various thing that you can do to increase the security in kubernetes

 > 

## Have you integrate your pipelines with sonartube

 > 

## You folks are using loki and prometheus and grafana, if u want to get get central logs how do i do that

 > 

## What do u understand by ingress default packet

 > 

## Lets say you have a very junior in your team who is very new in terms of kubernets, he doesnt know much about it that pod is not getting scheduled

 > Describe the pods 
 > Check the logs

## Is there any way to provide external network connectivity to kubernetes

 > 

## How can we forward the port 8080 of a container to a svc and then to ingress and then to browser 80 port