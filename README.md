# UI as Microservices with Spring Cloud Gateway and angular 1 and 5

---
This article is going to show you how to develop UI as multiple UI microsevices, in other words I am going to apply microservice concept to a UI. If this is done right, it gives us a number of benefits, for example autonomous build pipelines and deployments, autonomous teams and so forth. 

Applying Microservice on the UI is not that common, I have seen examples using [web components](http://bit.ly/web-components-ui-composition), [server-side UI compostion](http://bit.ly/composite-UI-based-microservice). Another interesting article uses [Spring gateway with multiple UIs](http://bit.ly/Multiple-UI-Applications-Gateway) article  All I can say its hard, but its doable.    

This article draws inspiration from a number of places. Having worked on large scale UI projects and experienced the pain, from slowness of delivering, hardiship of migrating from angular 1.x to 5. This article also draws insipiration from Eric Evans's serminal book [Domain-Driven-Design](http://bit.ly/ddd-eric-evans), and [Vaugn Vernon](http://bit.ly/ddd-vv). I also drew some inspiration from microservices, in particular, [Sam Newman Ground-breaking book](http://bit.ly/microservices-sm) 

---
**You can view a live demo by clicking the image below.**
[![Main container application](/images/main.png)](https://med101.herokuapp.com/)
Figure 1 Main container application, Angular 5 and Spring-boot.

**[View the demo on heroku](https://med101.herokuapp.com/)**

---

## The business problem.
We are going to build standalone UI applications that function as one application to deliver seamless patient experience, from patient own booking app, staff booking app, doctor consultation app and payment application. We are going to use different versions of angular (1.x and 5), just to illustrate the ability to be UI framework agnostic when we break our UI into microservices. Our application is composed of the following UI microservices:
1. Main UI microservice **(angular 5)**.
2. Patient booking UI microservice **(angular 5)**.
3. Staff booking managment UI microservice **(angular 5)**.
4. Doctor consultation management microservice **(angular 5)**.
5. Payments managment UI **(angular 1.5)**

## Application Boundaries
My motivation for breacking the UI as above, is to show you how to apply microservice thinking to a monlithic UI, this is problem you need to pay close attention. I have seen people breaking UI into technical components, you will cry if you do this. In DDD the concept of [bounded context](http://bit.ly/bounded-context) encourages us to breaking-up our domain models around business capabilities. I prefer to lean more torwards [Self-Contained-Systems](http://bit.ly/2JcwAtm). 

## Iterations   
    
### 1. [Creating Gateway Main UI microservice with **(Angular 5, Spring-boot and Zuul gateway)**](https://github.com/cleophasmashiri/Patient-Management-UI-Microsevices/blob/master/docs/part1/README.md)
### 2. [Creating Child UI microservices with **(Angular 5, Spring-boot)**](https://github.com/cleophasmashiri/Patient-Management-UI-Microsevices/blob/master/docs/part2/README.md)
### 3. [Creating Child UI microservice with **(Angular 1.5, Spring-boot)**](https://github.com/cleophasmashiri/Patient-Management-UI-Microsevices/blob/master/docs/part3/README.md)
### 4. [Deploy to **Heroku**](https://github.com/cleophasmashiri/Patient-Management-UI-Microsevices/blob/master/docs/part4/README.md)
### 5. [Add Configuration microservice with **(Spring Cloud Configuration Service)**](https://github.com/cleophasmashiri/Patient-Management-UI-Microsevices/blob/master/docs/part5/README.md)

## How to run the apps.

 . cd to Patient-Management-UI-Microsevices folder and run the following
 Unix or Mac os
```
 ./main/mvnw spring-boot:run && ./patient/mvnw spring-boot:run && ./doctor/mvnw spring-boot:run && ./payment/mvnw spring-boot:run && ./booking/mvnw spring-boot:run
```

**[View the demo on heroku](https://med101.herokuapp.com/)**


