---
title: "방법: 비동기 데이터 서비스 쿼리 실행(WCF Data Service) | Microsoft Docs"
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
  - "비동기 작업 [WCF Data Services]"
  - "WCF Data Services, 비동기 작업"
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 비동기 데이터 서비스 쿼리 실행(WCF Data Service)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하여 쿼리 실행, 변경 내용 저장과 같은 클라이언트\-서버 작업을 비동기적으로 수행할 수 있습니다. 자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)을 참조하세요.  
  
> [!NOTE]
>  지정된 스레드에 대해 콜백을 호출해야 하는 응용 프로그램에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 메서드 실행을 명시적으로 마샬링해야 합니다.  자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)을 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> 메서드 호출을 통해 쿼리를 시작하여 비동기 쿼리를 실행하는 방법을 보여 줍니다.  인라인 대리자는 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 메서드를 호출하여 쿼리 결과를 표시합니다.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)