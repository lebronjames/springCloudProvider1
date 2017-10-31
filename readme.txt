服务提供者。系统版本：SpringBoot：1.3.5.RELEASE ，SpringCloud：Brixton.RELEASE
1) pom.xml引入
Eureka的client端（spring-cloud-starter-eureka） 
2) Application主类增加@EnableDiscoveryClient，激活Eureka中的DiscoveryClient实现
3) Controller注入@Autowired
    private DiscoveryClient client;
    调用：ServiceInstance instance = client.getLocalServiceInstance();
http://localhost:2222/add?a=1&b=2