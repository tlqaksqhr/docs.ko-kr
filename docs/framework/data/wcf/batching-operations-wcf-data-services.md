---
title: "일괄 처리 작업(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e929e9771ba1d47016919f017f3476b17581d8a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="batching-operations-wcf-data-services"></a>일괄 처리 작업(WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 지원 일괄 처리에 대 한 요청을 처리 한 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-기반 서비스입니다. 자세한 내용은 참조 [OData: 일괄 처리](http://go.microsoft.com/fwlink/?LinkId=186075)합니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], 각 작업을 사용 하는 <xref:System.Data.Services.Client.DataServiceContext>, 같은 쿼리를 실행 하거나 결과 데이터 서비스에 전송 되는 별도 요청에 변경 내용을 저장 합니다. 작업 집합에 대해 논리적 범위를 유지하려면 작업 일괄 처리를 명시적으로 정의합니다. 이렇게 하면 일괄 처리의 모든 작업이 단일 HTTP 요청에 데이터 서비스에 전송, 서버가 작업을 개별적으로 처리할 수 있도록 데이터 서비스와 왕복 수를 줄입니다.  
  
## <a name="batching-query-operations"></a>쿼리 작업 일괄 처리  
 여러 쿼리를 단일 일괄 처리로 실행하려면 일괄 처리의 각 쿼리를 별도의 <xref:System.Data.Services.Client.DataServiceRequest%601> 클래스 인스턴스로 만들어야 합니다. 이런 방식으로 쿼리 요청을 만들면 쿼리 자체가 URI로 정의되며 리소스의 주소 지정 규칙을 따릅니다. 자세한 내용은 참조 [데이터 서비스 리소스 액세스](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)합니다. 쿼리 요청 개체가 포함된 <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> 메서드를 호출하면 일괄 처리된 쿼리 요청 결과가 데이터 서비스로 전송됩니다. 이 메서드는 일괄 처리에 포함된 개별 쿼리에 대한 응답을 나타내며 각각 쿼리에서 반환된 개체 컬렉션이나 오류 정보를 포함하는 <xref:System.Data.Services.Client.DataServiceResponse> 개체의 컬렉션인 <xref:System.Data.Services.Client.QueryOperationResponse%601> 개체를 반환합니다. 일괄 처리에서 단일 쿼리 작업이 실패하면 <xref:System.Data.Services.Client.QueryOperationResponse%601> 개체에 실패한 작업에 대한 오류 정보가 반환되며 나머지 작업은 계속 실행됩니다. 자세한 내용은 참조 [하는 방법: 일괄 처리에서 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md)합니다.  
  
 일괄 처리된 쿼리를 비동기적으로 실행할 수도 있습니다. 자세한 내용은 참조 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)합니다.  
  
## <a name="batching-the-savechanges-operation"></a>SaveChanges 작업 일괄 처리  
 호출 하는 경우는 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 메서드를 트랙으로 전송 되는 REST 기반 작업으로 변환 된 결과 컨텍스트 하도록 요청 하는 모든 변경 내용을 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스입니다. 기본적으로 이러한 변경 내용은 단일 요청 메시지로 전송되지 않습니다. 모든 변경 내용을 단일 요청에서 보낼 수를 요구 하려면 호출 해야 합니다는 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> 메서드 값을 포함 하 고 <xref:System.Data.Services.Client.SaveChangesOptions.Batch> 에 <xref:System.Data.Services.Client.SaveChangesOptions> 메서드에 제공 하는 열거형입니다.  
  
 일괄 처리된 변경 내용을 비동기적으로 저장할 수도 있습니다. 자세한 내용은 참조 [비동기 작업](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
