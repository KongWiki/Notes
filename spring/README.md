## SSM整合易忘点

### ==整合dao层==

1. 基础的==xml==配置

   1. mybatis

      ```xml
      <?xml version="1.0" encoding="UTF-8" ?>
      <!DOCTYPE configuration
              PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
              "http://mybatis.org/dtd/mybatis-3-config.dtd">
      <configuration>
         
      </configuration>
      ```

   2. spring基础

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <beans xmlns="http://www.springframework.org/schema/beans"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:schemaLocation="http://www.springframework.org/schema/beans
              https://www.springframework.org/schema/beans/spring-beans.xsd">
      
          <import resource="spring-dao.xml"/>
          <import resource="spring-service.xml"/>
      </beans>
      ```

   3. spring-dao 4个

      ```xml
      <context:property-placeholder location="classpath:jdbc.properties"/>
      <bean id="dataSource" class="com.mchange.v2.c3p0.ComboPooledDataSource">...</bean>
      <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">...</bean>
      <bean class="org.mybatis.spring.mapper.MapperScannerConfigurer">...</bean>
      ```

   4. sppring-service 3个

      ```xml
      <context:component-scan base-package="com.wkk.service"/>
      <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">...</bean>
      <tx:annotation-driven transaction-manager="transactionManager"/>
      ```

   5. spring-controller 4个

      ```xml
      <context:component-scan base-package="com.wkk.controller"/>
      <mvc:annotation-driven/>
      <mvc:default-servlet-handler/>
      <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
          <property name="prefix" value="/WEB-INF/jsp/"/>
          <property name="suffix" value=".jsp"/>
      </bean>
      ```

      

      

