---
title: "웹 브라우저에서 서비스 액세스(WCF Data Services 퀵 스타트) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 웹 브라우저에서 서비스 액세스(WCF Data Services 퀵 스타트)
이 작업에서는 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 시작하고 웹 브라우저에서 선택적으로 피드 읽기를 사용하지 않도록 설정합니다.  그런 다음 서비스 정의 문서를 검색하고 웹 브라우저를 통해 HTTP GET 요청을 노출된 리소스로 전송하여 데이터 서비스 리소스에 액세스합니다.  
  
> [!NOTE]
>  기본적으로 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서는 사용자 컴퓨터에서 `localhost` URI에 포트 번호를 자동으로 할당합니다.  이 작업에서는 URI 예제에서 포트 번호 `12345`를 사용합니다.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 프로젝트에 특정 포트 번호를 설정하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)를 참조하세요.  
  
### Internet Explorer를 사용하여 기본 서비스 문서를 요청하려면  
  
1.  Internet Explorer의 **도구** 메뉴에서 **인터넷 옵션**을 선택하고 **내용** 탭, **설정**을 차례로 클릭한 다음 **피드 읽기용 보기 사용**의 선택을 취소합니다.  
  
     이렇게 하면 피드 읽기가 사용되지 않습니다.  이 기능을 사용하지 않도록 설정하지 않으면 웹 브라우저에서 원시 XML 데이터를 표시하지 않고 반환된 AtomPub 인코딩 문서를 XML 피드로 처리합니다.  
  
    > [!NOTE]
    >  브라우저에서 피드를 원시 XML 데이터로 표시할 수 없는 경우 피드를 페이지의 소스 코드로 볼 수 있어야 합니다.  
  
2.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 F5 키를 눌러 응용 프로그램 디버깅을 시작합니다.  
  
3.  로컬 컴퓨터에서 웹 브라우저를 엽니다.  주소 표시줄에 다음 URI를 입력합니다.  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     이 데이터 서비스에서 노출하는 엔터티 집합 목록을 포함하는 기본 서비스 문서가 반환됩니다.  
  
### 웹 브라우저에서 엔터티 집합 리소스에 액세스하려면  
  
1.  웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     Northwind 샘플 데이터베이스의 모든 고객 집합이 반환됩니다.  
  
2.  웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     특정 고객 `ALFKI`의 엔터티 인스턴스가 반환됩니다.  
  
3.  웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     고객과 주문 간의 관계가 이동되어 특정 고객 `ALFKI`에 대한 모든 주문 집합이 반환됩니다.  
  
4.  웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     제공한 `OrderID` 값을 기반으로 특정 주문만 반환되도록 특정 고객 `ALFKI`에 속하는 주문이 필터링됩니다.  
  
## 다음 단계  
 웹 브라우저에서 성공적으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 액세스했으며 브라우저가 지정된 리소스로 HTTP GET 요청을 보냅니다.  웹 브라우저를 사용하면 간편하게 요청의 주소 지정 구문을 실행해 보고 그 결과를 볼 수 있습니다.  그러나 프로덕션 데이터 서비스는 대개 이 방법으로 액세스되지 않습니다.  일반적으로 응용 프로그램은 응용 프로그램 코드나 스크립팅 언어를 통해 데이터 서비스와 상호 작용합니다. 다음으로 클라이언트 라이브러리를 사용하여 CLR\(공용 언어 런타임\) 개체인 것처럼 데이터 서비스 리소스에 액세스하는 클라이언트 응용 프로그램을 만듭니다.  
  
 [.NET Framework 클라이언트 응용 프로그램 만들기](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## 참고 항목  
 [데이터 서비스 리소스 액세스](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)