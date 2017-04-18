---
title: "방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드
Svcutil.exe를 사용하면 실행 중인 서비스에서 메타데이터를 다운로드하여 로컬 파일에 저장할 수 있습니다.HTTP 및 HTTPS URL 스키마의 경우 Svcutil.exe에서 WS\-MetadataExchange 및 [XML Web services 검색](http://go.microsoft.com/fwlink/?LinkId=94950)\(영문 페이지일 수 있음\)을 사용하여 메타데이터를 검색합니다.기타 URL 스키마의 경우 Svcutil.exe에서 WS\-MetadataExchange만 사용합니다.  
  
 기본적으로 Svcutil.exe는 <xref:System.ServiceModel.Description.MetadataExchangeBindings> 클래스에 정의된 바인딩을 사용합니다.WS\-MetadataExchange에 사용되는 바인딩을 구성하려면 `IMetadataExchange` 계약을 사용하고 메타데이터 끝점 주소의 URI\(Uniform Resource Identifier\) 스키마와 이름이 같은 Svcutil.exe\(svcutil.exe.config\)의 구성 파일에서 클라이언트 끝점을 정의해야 합니다.  
  
> [!CAUTION]
>  Svcutil.exe를 실행하여 각각 같은 이름의 작업이 포함된 서로 다른 두 서비스 계약을 노출하는 서비스의 메타데이터를 가져오는 경우, Svcutil.exe에 “메타데이터를 가져올 수 없습니다..”라는 오류가 표시됩니다. Get\(Car c\) 작업이 포함된 ICarService 서비스 계약을 노출하는 서비스가 Get\(Book b\) 작업이 포함된 IBookService 서비스 계약도 노출하는 경우를 예로 들 수 있습니다.이 문제를 해결하려면 다음 중 하나를 수행합니다.  
>   
>  -   작업 중 하나의 이름을 바꿉니다.  
> -   <xref:System.ServiceModel.OperationContractAttribute.Name%2A>을 다른 이름으로 설정합니다.  
> -   <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 사용하여 작업 중 하나의 네임스페이스를 다른 네임스페이스로 설정합니다.  
  
### Svcutil.exe를 사용하여 메타데이터를 다운로드하려면  
  
1.  다음 위치에서 Svcutil.exe 도구를 찾습니다.  
  
     C:\\Program Files\\Microsoft SDKs\\Windows\\v1.0.\\bin  
  
2.  명령 프롬프트에서 다음 형식을 사용하여 이 도구를 실행합니다.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     메타데이터를 다운로드하려면 `/t:metadata` 옵션을 지정해야 합니다.그렇지 않으면 클라이언트 코드와 구성이 생성됩니다.  
  
3.  \<`url`\>인수는 메타데이터를 제공하는 서비스 끝점의 URL 또는 온라인으로 호스팅되는 메타데이터 문서의 URL을 지정합니다.\<`epr`\> 인수는 WS\-MetadataExchange를 지원하는 서비스 끝점에 대한 WS\-Addressing `EndpointAddress`가 포함된 XML 파일의 경로를 지정합니다.  
  
 메타데이터를 다운로드하기 위한 이 도구 사용에 대한 옵션은 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 참조하십시오.  
  
## 예제  
 다음 명령은 실행 중인 서비스에서 메타데이터 문서를 다운로드합니다.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## 참고 항목  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)