---
title: "방법: DataServiceContext에 기존 엔터티 연결(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 데이터 변경"
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: DataServiceContext에 기존 엔터티 연결(WCF Data Services)
데이터 서비스에 엔터티가 이미 있으면 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리에서 먼저 쿼리를 실행하지 않고 엔터티를 나타내는 개체를 <xref:System.Data.Services.Client.DataServiceContext>에 직접 연결할 수 있습니다.  자세한 내용은 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제에서는 데이터 서비스에 저장될 변경 내용이 포함되어 있는 기존 `Customer` 개체를 만드는 방법을 보여 줍니다.  개체가 컨텍스트에 연결되고 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 메서드가 호출되어 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하기 전에 연결된 개체를 <xref:System.Data.Services.Client.EntityStates>로 표시합니다.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)