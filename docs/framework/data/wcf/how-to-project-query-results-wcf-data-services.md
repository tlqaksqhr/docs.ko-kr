---
title: "방법: 프로젝트 쿼리 결과(WCF Data Services)"
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
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80c6216315ca1fb1200e12bca89ae8ef27652947
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-project-query-results-wcf-data-services"></a>방법: 프로젝트 쿼리 결과(WCF Data Services)
프로젝션은 엔터티의 특정 속성만 응답에서 반환되도록 지정하여 쿼리에서 반환되는 데이터의 양을 줄이는 메커니즘을 제공합니다. 결과에 예측을 수행할 수 있습니다는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 를 사용 하 여 쿼리는 `$select` 쿼리 옵션 또는 사용 하 여는 [선택](~/docs/csharp/language-reference/keywords/select-clause.md) 절 ([선택](~/docs/visual-basic/language-reference/queries/select-clause.md) Visual basic에서) LINQ 쿼리에서 합니다. 자세한 내용은 참조 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 완료 하면이 서비스 및 클라이언트 데이터 클래스 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 Customers 엔터티를 새로운 CustomerAddress 형식으로 프로젝션하는 LINQ 쿼리를 보여 줍니다. 이 형식에는 주소 관련 속성과 ID 속성만 포함됩니다. 이 `CustomerAddress` 클래스는 클라이언트에서 정의되며 클라이언트 라이브러리가 엔터티 형식으로 인식할 수 있도록 특성이 지정됩니다.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>예  
 다음 예제에서는 반환된 Customers 엔터티를 새로운 CustomerAddressNonEntity 형식으로 프로젝션하는 LINQ 쿼리를 보여 줍니다. 이 형식에는 주소 관련 속성만 포함되고 ID 속성은 포함되지 않습니다. 이 `CustomerAddressNonEntity` 클래스는 클라이언트에서 정의되며 엔터티 형식으로 특성이 지정되지 않습니다.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>예  
 다음 예제에서는의 정의 `CustomerAddress``CustomerAddressNonEntity` 앞의 예제에 사용 되는 형식입니다.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]
