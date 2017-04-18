---
title: "방법: 일괄 처리로 쿼리 실행(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, 일괄 처리 요청"
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 일괄 처리로 쿼리 실행(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하면 데이터 서비스에 대한 두 개 이상의 쿼리를 단일 일괄 처리로 실행할 수 있습니다.  자세한 내용은 [일괄 처리 작업](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제에서는 Northwind 데이터 서비스에서 `Customers` 개체와 `Products` 개체를 모두 반환하는 쿼리가 포함된 <xref:System.Data.Services.Client.DataServiceRequest%601> 개체 배열을 실행하는 <xref:Microsoft.SqlServer.ReportingServices.ReportingService.ExecuteBatch%2A> 메서드를 호출하는 방법을 보여 줍니다.  반환된 <xref:System.Data.Services.Client.DataServiceResponse>의 <xref:System.Data.Services.Client.QueryOperationResponse%601> 개체 컬렉션이 열거되고 각 <xref:System.Data.Services.Client.QueryOperationResponse%601>에 포함되어 있는 개체 컬렉션도 열거됩니다.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)