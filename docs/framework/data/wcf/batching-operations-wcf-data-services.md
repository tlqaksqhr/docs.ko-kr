---
title: "일괄 처리 작업(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 클라이언트 라이브러리"
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 일괄 처리 작업(WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스에 대한 요청의 일괄 처리를 지원합니다.  자세한 내용은 [OData: 일괄 처리](http://go.microsoft.com/fwlink/?LinkId=186075)\(영문\)를 참조하세요. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 쿼리 실행, 변경 사항 저장과 같이 <xref:System.Data.Services.Client.DataServiceContext>를 사용하는 작업을 실행할 때마다 별도의 요청이 데이터 서비스로 전송됩니다.  작업 집합에 대해 논리적 범위를 유지하려면 작업 일괄 처리를 명시적으로 정의합니다.  이렇게 하면 일괄 처리의 모든 작업이 단일 HTTP 요청으로 데이터 서비스에 전송되고, 서버에서 작업을 개별적으로 처리할 수 있으며, 데이터 서비스에 대한 왕복 수가 줄어듭니다.  
  
## 쿼리 작업 일괄 처리  
 여러 쿼리를 단일 일괄 처리로 실행하려면 일괄 처리의 각 쿼리를 별도의 <xref:System.Data.Services.Client.DataServiceRequest%601> 클래스 인스턴스로 만들어야 합니다.  이런 방식으로 쿼리 요청을 만들면 쿼리 자체가 URI로 정의되며 리소스의 주소 지정 규칙을 따릅니다.  자세한 내용은 [데이터 서비스 리소스 액세스](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)을 참조하세요.  쿼리 요청 개체가 포함된 <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> 메서드를 호출하면 일괄 처리된 쿼리 요청 결과가 데이터 서비스로 전송됩니다.  이 메서드는 일괄 처리에 포함된 개별 쿼리에 대한 응답을 나타내며 각각 쿼리에서 반환된 개체 컬렉션이나 오류 정보를 포함하는 <xref:System.Data.Services.Client.QueryOperationResponse%601> 개체의 컬렉션인 <xref:System.Data.Services.Client.DataServiceResponse> 개체를 반환합니다.  일괄 처리에서 단일 쿼리 작업이 실패하면 <xref:System.Data.Services.Client.QueryOperationResponse%601> 개체에 실패한 작업에 대한 오류 정보가 반환되며 나머지 작업은 계속 실행됩니다.  자세한 내용은 [방법: 일괄 처리로 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md)을 참조하세요.  
  
 일괄 처리된 쿼리를 비동기적으로 실행할 수도 있습니다.  자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)을 참조하세요.  
  
## SaveChanges 작업 일괄 처리  
 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 호출하면 컨텍스트에서 추적하는 모든 변경 내용이 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스에 대한 요청으로 전송되는 REST 기반 작업으로 변환됩니다.  기본적으로 이러한 변경 내용은 단일 요청 메시지로 전송되지 않습니다.  모든 변경 내용을 단일 요청으로 보내도록 하려면 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> 메서드를 호출하고 메서드에 제공하는 <xref:System.Data.Services.Client.SaveChangesOptions> 열거형에 <xref:System.Data.Services.Client.SaveChangesOptions> 값을 포함해야 합니다.  
  
 일괄 처리된 변경 내용을 비동기적으로 저장할 수도 있습니다.  자세한 내용은 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)을 참조하세요.  
  
## 참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)