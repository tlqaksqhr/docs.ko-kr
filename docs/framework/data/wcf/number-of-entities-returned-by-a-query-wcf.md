---
title: "방법: 쿼리가 반환하는 엔터티의 수 확인(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d80e18f780ac164ae83e538c714fc770f4d36e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>방법: 쿼리가 반환하는 엔터티의 수 확인(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하여 쿼리 URI에 지정된 엔터티 집합에 있는 엔터티 수를 확인할 수 있습니다. 이 수는 쿼리 결과와 함께 포함되거나 정수 값으로 포함될 수 있습니다. 자세한 내용은 참조 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 완료 하면이 서비스 및 클라이언트 데이터 클래스 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> 메서드를 호출한 후 쿼리를 실행합니다. <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> 속성은 `Customers` 엔터티 집합에 있는 엔터티 수를 반환합니다.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>예  
 이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하여 `Customers` 엔터티 집합에 있는 엔터티 수인 정수 값만 반환합니다.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
