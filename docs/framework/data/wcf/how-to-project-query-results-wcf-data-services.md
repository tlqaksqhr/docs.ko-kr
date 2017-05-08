---
title: "방법: 쿼리 결과 프로젝션(WCF Data Services) | Microsoft Docs"
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
  - "프로젝션 [WCF Data Services]"
  - "쿼리 프로젝션 [WCF Data Services]"
  - "WCF Data Services, 프로젝션"
  - "WCF Data Services, 쿼리"
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 방법: 쿼리 결과 프로젝션(WCF Data Services)
프로젝션은 엔터티의 특정 속성만 응답에서 반환되도록 지정하여 쿼리에서 반환되는 데이터의 양을 줄이는 메커니즘을 제공합니다.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 쿼리 옵션을 사용하거나 LINQ 쿼리에서 `$select`select 절\(Visual Basic에서는 [Select](../Topic/select%20clause%20\(C%23%20Reference\).md)\)을 사용하여 [쿼리의 결과에 대해 프로젝션을 수행할 수 있습니다.](../Topic/Select%20Clause%20\(Visual%20Basic\).md) 자세한 내용은 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)를 참조하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다.  이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어집니다.  
  
## 예제  
 다음 예제에서는 Customers 엔터티를 새로운 CustomerAddress 형식으로 프로젝션하는 LINQ 쿼리를 보여 줍니다. 이 형식에는 주소 관련 속성과 ID 속성만 포함됩니다.  이 `CustomerAddress` 클래스는 클라이언트에서 정의되며 클라이언트 라이브러리가 엔터티 형식으로 인식할 수 있도록 특성이 지정됩니다.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## 예제  
 다음 예제에서는 반환된 Customers 엔터티를 새로운 CustomerAddressNonEntity 형식으로 프로젝션하는 LINQ 쿼리를 보여 줍니다. 이 형식에는 주소 관련 속성만 포함되고 ID 속성은 포함되지 않습니다.  이 `CustomerAddressNonEntity` 클래스는 클라이언트에서 정의되며 엔터티 형식으로 특성이 지정되지 않습니다.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## 예제  
 다음 예제에서는 이전 예제에서 사용된 `CustomerAddress` `CustomerAddressNonEntity` 형식의 정의를 보여 줍니다.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]