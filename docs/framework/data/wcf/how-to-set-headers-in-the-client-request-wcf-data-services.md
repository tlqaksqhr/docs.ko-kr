---
title: "방법: 클라이언트 요청의 헤더 설정(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 요청 사용자 지정"
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 클라이언트 요청의 헤더 설정(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하여 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을 지원하는 데이터 서비스에 액세스할 때 클라이언트 라이브러리에서 데이터 서비스로 전송되는 요청 메시지의 필수 HTTP 헤더를 자동으로 설정합니다.  하지만 클라이언트 라이브러리는 데이터 서비스에 청구 기반 인증이나 쿠키가 필요한 경우와 같은 특정 상황에서 필요한 메시지 헤더를 설정하지 못합니다.  자세한 내용은 [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication)을 참조하세요.  이런 경우에는 전송하기 전에 요청 메시지의 메시지 헤더를 수동으로 설정해야 합니다.  이 항목의 예제에서는 데이터 서비스로 전송하기 전에 요청 메시지에 새로운 헤더를 추가하도록 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 이벤트를 처리하는 방법을 설명합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]웹 사이트에 게시된 [Northwind 샘플 데이터 서비스](http://go.microsoft.com/fwlink/?LinkId=187426)를 사용할 수도 있습니다. 이 샘플 데이터 서비스는 읽기 전용이므로 변경 내용을 저장하려고 하면 오류가 발생합니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 웹 사이트의 샘플 데이터 서비스는 익명 인증을 허용합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>이벤트에 대한 처리기를 등록한 다음 데이터 서비스에 대해 쿼리를 실행합니다.  
  
> [!NOTE]
>  데이터 서비스에서 모든 요청의 메시지 헤더를 수동으로 설정하도록 요구하는 경우 데이터 서비스를 나타내는 엔터티 컨테이너\(이 경우에는 `NorthwindEntities`\)에서 `OnContextCreated` 부분 메서드를 재정의하여 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 이벤트 처리기를 등록하는 것이 좋습니다.  
  
 [!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]
 [!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]  
  
## 예제  
 다음 메서드가 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 이벤트를 처리하고 인증 헤더를 요청에 추가합니다.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## 참고 항목  
 [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)