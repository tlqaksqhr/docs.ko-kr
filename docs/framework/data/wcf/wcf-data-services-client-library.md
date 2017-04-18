---
title: "WCF Data Services 클라이언트 라이브러리 | Microsoft Docs"
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
  - "DataServiceContext 클래스, DataServiceContext 클래스 정보"
  - "DataServiceQuery 클래스, DataServiceQuery 클래스 정보"
  - "WCF Data Services, 클라이언트 라이브러리"
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF Data Services 클라이언트 라이브러리
모든 응용 프로그램은 HTTP 요청을 전송하고 데이터 서비스가 반환하는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 처리할 수 있는 경우 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 기반 데이터 서비스와 상호 작용할 수 있습니다. 이러한 상호 운용성을 통해 광범위한 웹 사용 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스에 액세스할 수 있습니다.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에는 .NET Framework 또는 Silverlight 기반 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용할 때 보다 다양한 기능을 갖춘 프로그래밍 환경을 제공하는 클라이언트 라이브러리가 포함되어 있습니다.  
  
 클라이언트 라이브러리의 두 가지 주요 클래스는 <xref:System.Data.Services.Client.DataServiceContext> 클래스와 <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스입니다.  <xref:System.Data.Services.Client.DataServiceContext> 클래스는 지정한 데이터 서비스에 대해 지원되는 작업을 캡슐화합니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스는 상태 비저장 특성을 갖지만 컨텍스트는 그렇지 않습니다.  따라서 변경 관리 등의 기능을 지원하기 위해 <xref:System.Data.Services.Client.DataServiceContext> 클래스를 사용하여 데이터 서비스와의 상호 작용 간에 클라이언트에서 상태를 유지할 수 있습니다.  또한 이 클래스는 ID를 관리하고 변경 내용을 추적합니다.  <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스는 특정 엔터티 집합에 대한 쿼리를 나타냅니다.  
  
 이 단원에서는 클라이언트 라이브러리를 사용하여 .NET Framework 클라이언트 응용 프로그램에서 데이터에 액세스하고 변경하는 방법에 대해 설명합니다.  Silverlight 기반 응용 프로그램에서 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하는 방법에 대한 자세한 내용은 [WCF Data Services\(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=186016)\(영문\)를 참조하세요.  다른 클라이언트 라이브러리를 사용하여 다른 종류의 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용할 수도 있습니다.  자세한 내용은 [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796)\(영문\)를 참조하세요.  
  
## 단원 내용  
 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 기반으로 하는 클라이언트 데이터 서비스 클래스 및 클라이언트 라이브러리를 생성하는 방법에 대해 설명합니다.  
  
 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 클라이언트 라이브러리를 사용하여 .NET Framework 기반 응용 프로그램에서 데이터 서비스를 쿼리하는 방법에 대해 설명합니다.  
  
 [지연된 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 초기 쿼리 응답에 포함되지 않은 추가 콘텐츠를 로드하는 방법에 대해 설명합니다.  
  
 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 클라이언트 라이브러리를 사용하여 엔터티와 관계를 만들고 수정 및 삭제하는 방법에 대해 설명합니다.  
  
 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 비동기 방식으로 데이터 서비스와 작업할 수 있도록 클라이언트 라이브러리에서 제공하는 기능에 대해 설명합니다.  
  
 [일괄 처리 작업](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 클라이언트 라이브러리를 사용하여 여러 요청을 데이터 서비스에 단일 일괄 처리로 보내는 방법에 대해 설명합니다.  
  
 [컨트롤에 데이터 바인딩](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 데이터 서비스에서 반환하는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 컨트롤을 바인딩하는 방법에 대해 설명합니다.  
  
 [서비스 작업 호출](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 클라이언트 라이브러리를 사용하여 서비스 작업을 호출하는 방법에 대해 설명합니다.  
  
 [데이터 서비스 컨텍스트 관리](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 클라이언트 라이브러리의 동작을 관리하는 옵션에 대해 설명합니다.  
  
 [이진 데이터로 작업](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 데이터 서비스에서 데이터 스트림으로 반환하는 이진 데이터에 액세스하고 해당 데이터를 변경하는 방법에 대해 설명합니다.  
  
## 참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)