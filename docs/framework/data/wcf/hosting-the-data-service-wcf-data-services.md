---
title: "데이터 서비스 호스팅(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "HTML"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "WCF Data Services, 구성"
  - "WCF Data Services, Windows Communication Foundation"
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 데이터 서비스 호스팅(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하여 데이터를 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드로 노출하는 서비스를 만들 수 있습니다.  이 데이터 서비스는 <xref:System.Data.Services.DataService%601>에서 상속되는 클래스로 정의됩니다.  이 클래스는 요청 메시지를 처리하고, 데이터 원본에 대한 업데이트를 수행하고, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]의 필요에 따라 응답 메시지를 생성하는 데 필요한 기능을 제공합니다. 그러나, 데이터 서비스는 수신되는 HTTP 요청에 대한 네트워크 소켓에 바인딩하고 대기할 수 없습니다.  이 필요한 기능을 위해 데이터 서비스는 호스팅 구성 요소를 사용합니다.  
  
 데이터 서비스 호스트는 데이터 서비스를 대신하여 다음 작업을 수행합니다.  
  
-   요청을 수신 대기하고 이러한 요청을 데이터 서비스로 라우트합니다.  
  
-   각 요청에 대한 데이터 서비스의 인스턴스를 만듭니다.  
  
-   데이터 서비스가 들어오는 요청을 처리하도록 요청합니다.  
  
-   데이터 서비스를 대신하여 응답을 보냅니다.  
  
 데이터 서비스 호스팅을 단순화하기 위해 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 WCF\(Windows Communication Foundation\)와 통합되도록 디자인되었습니다.  데이터 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에서 데이터 서비스 호스트 역할을 하는 기본 WCF 구현을 제공합니다.  따라서 다음 방법 중 하나로 데이터 서비스를 호스트할 수 있습니다.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에서  
  
-   자체 호스팅 WCF 서비스를 지원하는 관리되는 응용 프로그램에서  
  
-   다른 사용자 지정 데이터 서비스 호스트에서  
  
## ASP.NET 응용 프로그램에서 데이터 서비스 호스팅  
 Visual Studio에서 **새 항목 추가** 대화 상자를 사용하여 ASP.NET 응용 프로그램에서 데이터 서비스를 정의하는 경우 프로젝트에 새로운 두 파일이 생성됩니다.  첫 번째 파일은 확장명이 `.svc`이고 데이터 서비스를 인스턴스화하는 방법을 WCF 런타임에 지시합니다.  경로 예제는 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어지는 Northwind 샘플 데이터 서비스에 대한 이 파일의 예제는 다음과 같습니다.  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 이 지시문은 <xref:System.Data.Services.DataServiceHostFactory> 클래스를 사용하여 명명된 데이터 서비스 클래스에 대한 서비스 호스트를 만들도록 응용 프로그램에 지시합니다.  
  
 `.svc` 파일의 코드 숨김 페이지에는 Northwind 샘플 데이터 서비스에 대해 다음과 같이 정의된 데이터 서비스 자체의 구현인 클래스가 포함되어 있습니다.  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 데이터 서비스가 WCF 서비스처럼 동작하기 때문에 데이터 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]과 통합되고 WCF 웹 프로그래밍 모델을 따릅니다. 자세한 내용은 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) 및 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)을 참조하세요.  
  
## 자체 호스팅 WCF 서비스  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 WCF 구현을 통합하기 때문에 데이터 서비스를 WCF 서비스로 자체 호스트하는 것을 지원합니다.  콘솔 응용 프로그램과 같은 모든 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램에 서비스를 자체 호스트할 수 있습니다.  <xref:System.ServiceModel.Web.WebServiceHost>에서 상속되는 <xref:System.Data.Services.DataServiceHost> 클래스는 특정 주소에서 데이터 서비스를 인스턴스화하는 데 사용됩니다.  
  
 셀프 호스팅을 개발과 테스트에 사용하면 서비스의 배포와 문제 해결이 보다 쉬워질 수 있습니다.  그러나 이러한 종류의 호스팅은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 또는 IIS\(인터넷 정보 서비스\)에서 제공하는 고급 호스팅 및 관리 기능을 제공하지 않습니다. 자세한 내용은 [관리되는 응용 프로그램에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)을 참조하세요.  
  
## 사용자 지정 데이터 서비스 호스트 정의  
 WCF 호스트 구현이 너무 제한적인 경우 데이터 서비스에 대한 사용자 지정 호스트도 정의할 수 있습니다.  <xref:System.Data.Services.IDataServiceHost> 인터페이스를 구현하는 모든 클래스를 데이터 서비스에 대한 네트워크 호스트로 사용할 수 있습니다.  사용자 지정 호스트는 <xref:System.Data.Services.IDataServiceHost> 인터페이스를 구현해야 하며 다음과 같은 데이터 서비스 호스트의 기본 임무를 처리할 수 있어야 합니다.  
  
-   데이터 서비스에 서비스 루트 경로를 제공합니다.  
  
-   적절한 <xref:System.Data.Services.IDataServiceHost> 멤버 구현에 대한 요청 및 응답 헤더 정보를 처리합니다.  
  
-   데이터 서비스에서 발생한 예외를 처리합니다.  
  
-   쿼리 문자열의 매개 변수 유효성을 검사합니다.  
  
## 참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [데이터를 서비스로 노출](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)   
 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)