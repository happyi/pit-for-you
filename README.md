# pit-for-you
填坑指南

坑1.spring  component-scan 和 spring-mvc  component-scan 同时配置会导致事物失效
fix:
spring :
```
<context:component-scan base-package="com.*" >
  <context:exclude-filter type="annotation" expression="org.springframework.stereotype.Controller" />
</context:component-scan>
```
spring-mvc:
```
<context:component-scan base-package="com.*" >
		<context:exclude-filter type="annotation" expression="org.springframework.stereotype.Repository"/>
		<context:exclude-filter type="annotation" expression="org.springframework.stereotype.Service"/>
</context:component-scan>
```
