# 전역 config 설정 테스트를 위한 레파지토리 입니다. 
---
## 실행, 동작

- 유레카 서버 > 컨피그 서버 > 상품 순으로 실행합니다.
- 상품이 실행될때 로그의 포트를 확인합니다. 19083 으로 할당됨을 볼 수 있습니다.
    
    
- http://localhost:19083/product 을 호출하면 포트와 메시지를 확인 할 수 있습니다.
        
- config-server 의 product-service-local.yml 파일의 message를 수정하고 config-server 를 재시작 합니다.
    
    ```java
    server:
      port: 19083
    
    message: "product-service-local message updated"
    ```
    
- talend api tester를 실행하고 http://localhost:19083/actuator/refresh 로 post 요청을 합니다. 응답으로 메시지가 업데이트 됨을 확인 할 수 있습니다.
        
- 다시 http://localhost:19083/product를 호출 하면 메시지가 변경된 것을 확인 할 수 있습니다.    

- *참고 http://localhost:18080/product-service/local 로 접속하면 product-service의 설정 값들을 볼수 있습니다.(이를 통해 다른 설정값들도 확인할 수 있습니다.)
    
