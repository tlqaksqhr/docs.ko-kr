---
title: "방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사
[ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스를 호스트하지 않고 서비스 구현과 구성에서 오류를 검색할 수 있습니다.  
  
### 서비스의 유효성을 검사하려면  
  
1.  서비스를 실행 파일과 하나 이상의 종속 어셈블리로 컴파일합니다.  
  
2.  SDK 명령 프롬프트를 엽니다.  
  
3.  명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다.  다양한 매개 변수에 대한 자세한 내용은 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 항목의 서비스 유효성 검사 단원을 참조하세요.  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     유효성을 검사할 서비스의 구성 이름을 나타내려면 `/serviceName` 옵션을 사용해야 합니다.  
  
     `assemblyPath` 인수는 유효성을 검사할 서비스 형식이 포함된 하나 이상의 어셈블리와 서비스에 대한 실행 파일 경로를 지정합니다.  서비스 구성을 제공하려면 실행 가능한 어셈블리에 연결된 구성 파일이 있어야 합니다.  표준 명령줄 와일드카드를 사용하여 여러 어셈블리를 제공할 수 있습니다.  
  
## 예제  
 다음 명령은 myServiceHost.exe 실행 파일에 구현된 myServiceName 서비스를 사용합니다.  서비스\(myServiceHost.exe.config\)에 대한 구성 파일이 자동으로 로드됩니다.  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## 참고 항목  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)