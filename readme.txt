服务提供者1。系统版本：SpringBoot：1.3.5.RELEASE ，SpringCloud：Brixton.RELEASE
1) pom.xml引入
Eureka的client端（spring-cloud-starter-eureka） 
2) Application主类增加@EnableDiscoveryClient，激活Eureka中的DiscoveryClient实现
3) Controller注入@Autowired
    private DiscoveryClient client;
    调用：ServiceInstance instance = client.getLocalServiceInstance();
http://localhost:2222/add?a=1&b=2
4) 系统参数配置
spring:
  application:
    name: compute-serviceB
server:
  port: 2223
eureka:
  client:
    serviceUrl:
      defaultZone: http://peer1:1111/eureka/,http://peer2:1112/eureka/