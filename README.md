# Java-Springboot


# What is Bean in Spring?
- A bean is an object that is instantiated , assembled , and otherwise managed by a Spring IOC (Inversion of Control - A process in which an object defines its dependencies without creating them)  container.

在 Java 配置 @Configuration 期間，將執行該方法並將其返回值註冊為 BeanFactory 中的 Bean.

Imagine an application with dozens or even hundreds of classes. Sometimes we want to share a single instance of a class across the whole application, other times we need a separate object for each use case, and so on.

Managing such a number of objects is nothing short of a nightmare. This is where inversion of control comes to the rescue. Instead of constructing dependencies by itself, an object can retrieve its dependencies from an IoC container. All we need to do is to provide the container with appropriate configuration metadata.


## Configuration class supplying bean metadata to an IoC container
```
@Configuration
@ComponentScan(basePackageClasses = Company.class)
public class Config {
    @Bean
    public Address getAddress() {
        return new Address("High Street", 1000);
    }
}


```

When a Spring IoC container constructs objects of those types, all the objects are called Spring beans, as they are managed by the IoC container.
