# springboot-super-pom

Along with the super-pom, we need application yml to follow below structure:

server:
  port: 8090

spring:
  application:
    name: common-test-client

logging.level:
  com.netflix.eureka: OFF
  com.netflix.discovery: OFF
  org.ahatech: INFO

eureka:
  client:
    service-url:
      defaultZone: http://localhost:8089/eureka, http://localhost:8088/eureka
    healthcheck:
      enabled: true
  
feign:
  client:
    config:
      default:
        connectTimeout: 5000
        readTimeout: 5000
        
management:
  endpoints:
    web:
      exposure:
        include: '*'
        exclude: shutdown
  endpoint:
    health:
      show-details: always
