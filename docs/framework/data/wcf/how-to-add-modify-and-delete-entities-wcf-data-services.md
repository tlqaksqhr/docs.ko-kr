---
title: "방법: 엔터티 추가, 수정 및 삭제(WCF Data Services) | Microsoft Docs"
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
ms.assetid: a00f8933-b232-4445-95ba-adc634f055d8
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 엔터티 추가, 수정 및 삭제(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하면 <xref:System.Data.Services.Client.DataServiceContext>에서 개체에 동등한 작업을 수행하여 데이터 서비스의 엔터티 데이터를 만들고 업데이트 및 삭제할 수 있습니다.  자세한 내용은 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제에서는 새 개체 인스턴스를 만든 다음 <xref:System.Data.Services.Client.DataServiceContext>의 <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> 메서드를 호출하여 컨텍스트의 항목을 만듭니다.  <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 HTTP POST 메시지가 데이터 서비스로 전송됩니다.  
  
 [!code-csharp[Astoria Northwind Client#AddProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addproduct)]
 [!code-vb[Astoria Northwind Client#AddProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addproduct)]  
  
## 예제  
 다음 예제에서는 기존 개체를 검색하고 수정한 다음 <xref:System.Data.Services.Client.DataServiceContext>의 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 메서드를 호출하여 컨텍스트의 항목을 업데이트됨으로 표시합니다.  <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 HTTP MERGE 메시지가 데이터 서비스로 전송됩니다.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#modifycustomer)]
 [!code-vb[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#modifycustomer)]  
  
## 예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext>의 <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> 메서드를 호출하여 컨텍스트의 항목을 삭제됨으로 표시합니다.  <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 HTTP DELETE 메시지가 데이터 서비스로 전송됩니다.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#deleteproduct)]
 [!code-vb[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#deleteproduct)]  
  
## 예제  
 다음 예제에서는 새 개체 인스턴스를 만든 다음 <xref:System.Data.Services.Client.DataServiceContext>의 <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> 메서드를 호출하여 관련 주문에 대한 링크와 함께 컨텍스트의 항목을 만듭니다.  <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 HTTP POST 메시지가 데이터 서비스로 전송됩니다.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [방법: DataServiceContext에 기존 엔터티 연결](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md)   
 [방법: 엔터티 관계 정의](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md)   
 [일괄 처리 작업](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)