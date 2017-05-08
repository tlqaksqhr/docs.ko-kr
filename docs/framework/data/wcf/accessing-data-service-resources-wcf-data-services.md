---
title: "데이터 서비스 리소스 액세스(WCF Data Services) | Microsoft Docs"
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
  - "시작, WCF Data Services"
  - "데이터 서비스 쿼리 [WCF Data Services]"
  - "WCF Data Services, 데이터 액세스"
  - "WCF Data Services, 시작"
  - "WCF Data Services, 쿼리"
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 데이터 서비스 리소스 액세스(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 URI로 주소를 지정할 수 있는 리소스가 포함된 피드로 데이터를 노출할 수 있도록 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을 지원합니다.  이러한 리소스는 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)의 엔터티\-관계 규칙에 따라 표현됩니다.  이 모델에서 엔터티는 고객, 주문, 항목 및 제품과 같이 응용 프로그램 도메인의 데이터 형식인 데이터 운영 단위를 나타냅니다.  REST\(Representational State Transfer\)의 의미 체계, 특히 GET, PUT, POST, DELETE 등의 표준 HTTP 동사를 사용하여 엔터티 데이터에 액세스하고 변경합니다.  
  
## 리소스 처리  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]에서는 URI를 사용하여 데이터 모델에서 노출하는 모든 데이터에 주소를 지정합니다.  예를 들어, 다음 URI는 Customer 엔터티 형식의 모든 인스턴스에 대한 항목이 포함된 Customers 엔터티 집합인 피드를 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 엔터티에는 엔터티 키라는 특수 속성이 있습니다.  엔터티 키는 엔터티 집합 내에서 단일 엔터티를 고유하게 식별하는 데 사용됩니다.  엔터티 키를 사용하면 엔터티 집합에 속한 특정 엔터티 형식 인스턴스의 주소를 지정할 수 있습니다.  예를 들어, 다음 URI는 키 값이 `ALFKI`인 Customer 엔터티 형식의 특정 인스턴스에 대한 항목을 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 엔터티 인스턴스의 기본 및 복합 속성에도 개별적으로 주소를 지정할 수 있습니다.  예를 들어, 다음 URI는 특정 고객의 `ContactName` 속성 값이 포함된 XML 요소를 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 이전 URI에 `$value` 끝점을 포함하는 경우 기본 속성의 값만 응답 메시지에 반환됩니다.  다음 예제에서는 XML 요소 없이 "Maria Anders" 문자열만 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 엔터티 간의 관계는 데이터 모델에서 연결에 의해 정의됩니다.  이러한 연결을 사용하면 엔터티 인스턴스의 탐색 속성을 사용하여 관련 엔터티의 주소를 지정할 수 있습니다.  탐색 속성은 다대일 관계의 경우 단일 관련 엔터티를 반환하고 일대다 관계의 경우 관련 엔터티의 집합을 반환할 수 있습니다.  예를 들어, 다음 URI는 특정 고객과 관련된 모든 주문의 집합인 피드를 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 대개 양방향인 관계는 탐색 속성 쌍으로 표현됩니다.  이전 예제에서 보여 준 관계와 반대로, 다음 URI는 특정 Order 엔터티가 속한 Customer 엔터티에 대한 참조를 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 사용하면 쿼리 식의 결과를 기준으로 리소스의 주소를 지정할 수도 있습니다.  이 경우 평가된 식을 기반으로 리소스 집합을 필터링할 수 있습니다.  예를 들어, 다음 URI는 1997년 9월 22일 이후에 운송된 특정 고객의 주문만 반환하도록 리소스를 필터링합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 자세한 내용은 [OData: URI 규칙](http://go.microsoft.com/fwlink/?LinkId=185564)\(영문\)을 참조하세요.  
  
## 시스템 쿼리 옵션  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]는 필터링, 정렬 및 페이징과 같은 일반적인 쿼리 작업을 리소스에 대해 수행하는 데 사용할 수 있는 시스템 쿼리 옵션의 집합을 정의합니다.  예를 들어, 다음 URI는 우편 번호가 `100`으로 끝나지 않는 관련 `Order_Detail` 엔터티와 함께 모든 `Order` 엔터티의 집합을 반환합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 또한 반환된 피드의 항목은 주문의 ShipCity 속성 값을 기준으로 정렬됩니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 다음 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 시스템 쿼리 옵션을 지원합니다.  
  
|쿼리 옵션|설명|  
|-----------|--------|  
|`$orderby`|반환된 피드의 엔터티에 대한 기본 정렬 순서를 정의합니다.  다음 쿼리는 반환된 고객 피드를 국가 및 도시를 기준으로 정렬합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> 자세한 내용은 [OData: OrderBy 시스템 쿼리 옵션\($orderby\)](http://go.microsoft.com/fwlink/?LinkId=186968)\(영문\)을 참조하세요.|  
|`$top`|반환된 피드에 포함할 엔터티의 수를 지정합니다.  다음 예제에서는 처음 10명의 고객을 건너뛰고 다음 10명의 고객을 반환합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> 자세한 내용은 [OData: Top 시스템 쿼리 옵션\($top\)](http://go.microsoft.com/fwlink/?LinkId=186969)\(영문\)을 참조하세요.|  
|`$skip`|피드의 엔터티 반환을 시작하기 전에 건너뛸 엔터티의 수를 지정합니다.  다음 예제에서는 처음 10명의 고객을 건너뛰고 다음 10명의 고객을 반환합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> 자세한 내용은 [OData: Skip 시스템 쿼리 옵션\($skip\)](http://go.microsoft.com/fwlink/?LinkId=186971)\(영문\)을 참조하세요.|  
|`$filter`|특정 조건에 따라 피드에서 반환되는 엔터티를 필터링하는 식을 정의합니다.  이 쿼리 옵션은 필터 식을 계산하는 데 사용되는 미리 정의된 쿼리 함수, 논리 비교 연산자 및 산술 연산자의 집합을 지원합니다.  다음 예제에서는 우편 번호가 100으로 끝나지 않는 모든 주문을 반환합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> 자세한 내용은 [OData: Filter 시스템 쿼리 옵션\($filter\)](http://go.microsoft.com/fwlink/?LinkId=186972)\(영문\)을 참조하세요.|  
|`$expand`|쿼리 결과로 반환되는 관련 엔터티를 지정합니다.  관련 엔터티는 쿼리 결과로 반환되는 엔터티와 함께 항목이나 피드로 포함됩니다.  다음 예제에서는 'ALFKI' 고객의 주문을 각 주문에 대한 항목 정보와 함께 반환합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> 자세한 내용은 [OData: Expand 시스템 쿼리 옵션\($expand\)](http://go.microsoft.com/fwlink/?LinkId=186973)\(영문\)을 참조하세요.|  
|`$select`|엔터티의 속성이 해당 프로젝션에 반환되도록 정의하는 프로젝션을 지정합니다.  기본적으로 엔터티의 모든 속성은 피드에 반환됩니다.  다음 쿼리는 `Customer` 엔터티의 세 속성만 반환합니다.<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> 자세한 내용은 [OData: Select 시스템 쿼리 옵션\($select\)](http://go.microsoft.com/fwlink/?LinkID=186076)\(영문\)을 참조하세요.|  
|`$inlinecount`|피드에 반환되는 엔터티 수가 피드와 함께 포함되도록 요청합니다.  자세한 내용은 [OData: Inlinecount 시스템 쿼리 옵션\($inlinecount\)](http://go.microsoft.com/fwlink/?LinkId=186975)\(영문\)을 참조하세요.|  
  
## 관계 주소 지정  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 사용하면 엔터티 집합과 엔터티 인스턴스의 주소를 지정하는 것 외에도 엔터티 간의 관계를 나타내는 연결의 주소를 지정할 수 있습니다.  이 기능은 Northwind 샘플 데이터베이스의 지정된 주문과 관련된 운송업체와 같이 두 엔터티 인스턴스 간의 관계를 만들거나 변경하는 데 필요합니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]에서는 `$link` 연산자를 사용하여 엔터티 간 연결의 주소를 지정하는 기능을 지원합니다.  예를 들어, 다음 URI는 HTTP PUT 요청 메시지에 지정되어 지정한 주문의 운송업체를 새 운송업체로 변경합니다.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 자세한 내용은 [OData: 항목 간 링크 주소 지정](http://go.microsoft.com/fwlink/?LinkId=187351)\(영문\)을 참조하세요.  
  
## 반환된 피드 사용  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 리소스의 URI를 사용하면 서비스에서 노출하는 엔터티 데이터의 주소를 지정할 수 있습니다.  웹 브라우저의 주소 필드에 URI를 입력하면 요청한 리소스의 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드 표현이 반환됩니다.  자세한 내용은 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 참조하세요.  데이터 서비스 리소스에서 필요한 데이터를 반환하는지 테스트하려면 웹 브라우저가 유용하지만, 데이터를 만들고 업데이트 및 삭제할 수도 있는 프로덕션 데이터 서비스는 일반적으로 웹 페이지의 응용 프로그램 코드나 스크립팅 언어를 통해 액세스됩니다.  자세한 내용은 [클라이언트 응용 프로그램에서 데이터 서비스 사용](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)을 참조하세요.  
  
## 참고 항목  
 [Open Data Protocol 웹 사이트 \(영문\)](http://go.microsoft.com/fwlink/?LinkID=182204)