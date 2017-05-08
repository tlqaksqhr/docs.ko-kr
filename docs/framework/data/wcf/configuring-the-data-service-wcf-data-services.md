---
title: "데이터 서비스 구성(WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, 구성"
ms.assetid: 59efd4c8-cc7a-4800-a0a4-d3f8abe6c55c
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 데이터 서비스 구성(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하여 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드를 노출하는 데이터 서비스를 만들 수 있습니다.  이러한 피드의 데이터는 다양한 데이터 소스에서 제공될 수 있습니다.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]는 데이터 공급자를 사용하여 이 데이터를 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드로 노출합니다.  이러한 공급자에는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 공급자, 리플렉션 공급자 및 사용자 지정 데이터 서비스 공급자 인터페이스의 집합이 포함됩니다.  공급자 구현은 서비스에 대한 데이터 모델을 정의합니다.  자세한 내용은 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)을 참조하세요.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 데이터 서비스는 데이터 서비스 형식이 데이터 모델의 엔터티 컨테이너인 <xref:System.Data.Services.DataService%601> 클래스에서 상속하는 클래스입니다.  이 엔터티 컨테이너에는 데이터 모델의 엔터티 집합에 액세스하는 데 사용되는 <xref:System.Linq.IQueryable%601>을 반환하는 속성이 하나 이상 들어 있습니다.  
  
 데이터 서비스의 동작은 <xref:System.Data.Services.DataServiceConfiguration> 클래스의 멤버 및 <xref:System.Data.Services.DataServiceConfiguration> 클래스의 <xref:System.Data.Services.DataServiceConfiguration.DataServiceBehavior%2A> 속성에서 액세스되는 <xref:System.Data.Services.DataServiceBehavior> 클래스의 멤버에 의해 정의됩니다.  <xref:System.Data.Services.DataServiceConfiguration> 클래스는 Northwind 데이터 서비스의 다음 구현과 같이 데이터 서비스에서 구현되는 `InitializeService` 메서드에 제공됩니다.  
  
 [!code-csharp[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigcomplete)]
 [!code-vb[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigcomplete)]  
  
## 데이터 서비스 구성 설정  
 <xref:System.Data.Services.DataServiceConfiguration> 클래스를 사용하면 다음 데이터 서비스 동작을 지정할 수 있습니다.  
  
|멤버|동작|  
|--------|--------|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptCountRequests%2A>|`$count` 경로 세그먼트와 `$inlinecount` 쿼리 옵션을 사용하여 데이터 서비스로 전송되는 개수 요청을 사용하지 않도록 설정할 수 있습니다.  자세한 내용은 [OData: URI 규칙](http://go.microsoft.com/fwlink/?LinkId=185564)\(영문\)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptProjectionRequests%2A>|`$select` 쿼리 옵션을 사용하여 데이터 서비스로 전송되는 데이터 프로젝션 지원을 사용하지 않도록 설정할 수 있습니다.  자세한 내용은 [OData: URI 규칙](http://go.microsoft.com/fwlink/?LinkId=185564)\(영문\)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeAccess%2A>|<xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 사용하여 정의된 동적 메타데이터 공급자의 메타데이터에 데이터 형식을 노출할 수 있습니다.|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeConversion%2A>|데이터 서비스 런타임이 페이로드에 포함된 형식을 요청에 지정된 실제 속성 형식으로 변환해야 하는지 여부를 지정할 수 있습니다.|  
|<xref:System.Data.Services.DataServiceBehavior.InvokeInterceptorsOnLinkDelete%2A>|두 엔터티 간의 관계 링크가 삭제될 때 관련 엔터티에 대해 등록된 변경 인터셉터를 호출할지 여부를 지정할 수 있습니다.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxBatchCount%2A>|단일 일괄 처리에서 허용되는 변경 집합과 쿼리 작업 수를 제한할 수 있습니다.  자세한 내용은 [OData: 배치](http://go.microsoft.com/fwlink/?LinkId=185602)\(영문\) 및 [일괄 처리 작업](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxChangesetCount%2A>|단일 변경 집합에 포함할 수 있는 변경 수를 제한할 수 있습니다.  자세한 내용은 [방법: 데이터 서비스 결과의 페이징 사용](../../../../docs/framework/data/wcf/how-to-enable-paging-of-data-service-results-wcf-data-services.md)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandCount%2A>|`$expand` 쿼리 연산자로 단일 요청에 포함할 수 있는 관련 엔터티 수를 제한하여 응답 크기를 제한할 수 있습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]은 [OData: URI 규칙](http://go.microsoft.com/fwlink/?LinkId=185564)\(영문\) 및 [지연된 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)를 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandDepth%2A>|`$expand` 쿼리 연산자로 단일 요청에 포함할 수 있는 관련 엔터티의 그래프 깊이를 제한하여 응답 크기를 제한할 수 있습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]은 [OData: URI 규칙](http://go.microsoft.com/fwlink/?LinkId=185564)\(영문\) 및 [지연된 콘텐츠 로드](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)를 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxObjectCountOnInsert%2A>|단일 POST 요청에 포함할 수 있는 삽입할 엔터티 수를 제한할 수 있습니다.|  
|<xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A>|데이터 서비스에 사용되는 Atom 프로토콜의 버전을 정의합니다.  <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> 값을 <xref:System.Data.Services.Common.DataServiceProtocolVersion>의 최대값보다 작은 값으로 설정하면 데이터 서비스에 액세스하는 클라이언트가 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]의 최신 기능을 사용할 수 없습니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [데이터 서비스 버전 관리](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxResultsPerCollection%2A>|데이터 피드로 반환되는 각 엔터티 집합의 엔터티 수를 제한하여 응답 크기를 제한할 수 있습니다.|  
|<xref:System.Data.Services.DataServiceConfiguration.RegisterKnownType%2A>|데이터 서비스에서 인식하는 형식 목록에 데이터 형식을 추가합니다.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetAccessRule%2A>|데이터 서비스에서 사용할 수 있는 엔터티 집합 리소스에 대한 액세스 권한을 설정합니다.  이름 매개 변수에 별표\(`*`\) 값을 제공하여 나머지 모든 엔터티 집합에 대한 액세스를 같은 수준으로 설정할 수 있습니다.  클라이언트 응용 프로그램에 필요한 데이터 서비스 리소스에 대한 최소 권한 액세스를 제공하도록 엔터티 집합에 대한 액세스를 설정하는 것이 좋습니다.  자세한 내용은 [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.  지정된 URI 및 HTTP 동작에 필요한 최소 액세스 권한의 예제는 [최소 리소스 액세스 요구 사항](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md#accessRequirements) 단원의 표를 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetPageSize%2A>|엔터티 집합 리소스의 최대 페이지 크기를 설정합니다.  자세한 내용은 [방법: 데이터 서비스 결과의 페이징 사용](../../../../docs/framework/data/wcf/how-to-enable-paging-of-data-service-results-wcf-data-services.md)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetServiceOperationAccessRule%2A>|데이터 서비스에 정의된 서비스 작업에 대한 액세스 권한을 설정합니다.  자세한 내용은 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)을 참조하세요.  이름 매개 변수에 별표\(`*`\) 값을 제공하여 모든 서비스 작업에 대한 액세스를 같은 수준으로 설정할 수 있습니다.  클라이언트 응용 프로그램에 필요한 데이터 서비스 리소스에 대한 최소 권한 액세스를 제공하도록 서비스 작업에 대한 액세스를 설정하는 것이 좋습니다.  자세한 내용은 [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.|  
|<xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A>|이 구성 속성을 사용하면 오류 응답 메시지에 더 많은 정보가 반환되므로 데이터 서비스 문제를 보다 쉽게 해결할 수 있습니다.  이 옵션은 프로덕션 환경에 사용하기에 적합하지 않습니다.  자세한 내용은 [WCF Data Services 개발 및 배포](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)을 참조하세요.|  
  
<a name="accessRequirements"></a>   
## 최소 리소스 액세스 요구 사항  
 다음 표에서는 특정 작업을 수행하기 위해 부여되어야 하는 최소 엔터티 집합 권한에 대해 설명합니다.  경로 예제는 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 완료하면 만들어지는 Northwind 데이터 서비스를 기반으로 합니다.  <xref:System.Data.Services.EntitySetRights> 열거형과 <xref:System.Data.Services.ServiceOperationRights> 열거형이 <xref:System.FlagsAttribute>를 사용하여 정의되기 때문에 논리 OR 연산자를 사용하여 단일 엔터티 집합이나 작업에 여러 사용 권한을 지정할 수 있습니다.  자세한 내용은 [방법: 데이터 서비스에 액세스할 수 있도록 설정](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)을 참조하세요.  
  
|경로\/동작|`GET`|`DELETE`|`MERGE`|`POST`|`PUT`|  
|------------|-----------|--------------|-------------|------------|-----------|  
|`/Customers`|<xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|<xref:System.Data.Services.EntitySetRights>|지원 안 함|  
|`/Customers('ALFKI')`|<xref:System.Data.Services.EntitySetRights>|<xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|<xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|해당 없음|<xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|  
|`/Customers('ALFKI')/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|`Customers`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights> 또는 <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders` `:` 및 <xref:System.Data.Services.EntitySetRights>|지원 안 함|  
|`/Customers('ALFKI')/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|지원 안 함|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|  
|`/Orders(10643)/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|지원 안 함|  
|`/Customers('ALFKI')/$links/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|`Customers`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights> 또는 <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|  
|`/Customers('ALFKI')/$links/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights> 또는 <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|지원 안 함|  
|`/Orders(10643)/$links/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|`Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights> 또는 <xref:System.Data.Services.EntitySetRights>|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|지원 안 함|`Customers`: <xref:System.Data.Services.EntitySetRights>;<br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|  
|`/Customers/$count`|<xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|지원 안 함|지원 안 함|  
|`/Customers('ALFKI')/ContactName`|<xref:System.Data.Services.EntitySetRights>|지원 안 함|<xref:System.Data.Services.EntitySetRights>|지원 안 함|<xref:System.Data.Services.EntitySetRights>|  
|`/Customers('ALFKI')/Address/StreetAddress/$value` <sup>1</sup>|<xref:System.Data.Services.EntitySetRights>|<xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|지원 안 함|  
|`/Customers('ALFKI')/ContactName/$value`|<xref:System.Data.Services.EntitySetRights>|<xref:System.Data.Services.EntitySetRights> 및 <xref:System.Data.Services.EntitySetRights>|<xref:System.Data.Services.EntitySetRights>|지원 안 함|<xref:System.Data.Services.EntitySetRights>|  
|`/Customers('ALFKI')/$value` <sup>2</sup>|<xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|지원 안 함|<xref:System.Data.Services.EntitySetRights>|  
|`/Customers?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|`Customers`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|  
|`/Customers('ALFKI')?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights><br /><br /> 및<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights>|지원 안 함|지원 안 함|지원 안 함|지원 안 함|  
  
 <sup>1</sup> 이 예제에서 `Address`는 `StreetAddress`라는 속성이 있는 `Customers` 엔터티의 복합 형식 속성을 나타냅니다.  Northwind 데이터 서비스에서 사용되는 모델은 이 복합 형식을 명시적으로 정의하지 않습니다.  데이터 모델이 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 공급자를 사용하여 정의된 경우 [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 도구를 사용하여 이러한 복합 형식을 정의할 수 있습니다.  자세한 내용은 [How to: Create and Modify Complex Types](http://msdn.microsoft.com/ko-kr/afb8e206-0ffe-4597-b6d4-6ab566897e1d)을 참조하세요.  
  
 <sup>2</sup> 이 URI는 BLOB\(Binary Large Object\)를 반환하는 속성이 미디어 링크 항목인 엔터티\(이 경우에는 `Customers`\)에 속한 미디어 리소스로 정의된 경우 지원됩니다.  자세한 내용은 [스트리밍 공급자](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)을 참조하세요.  
  
<a name="versioning"></a>   
## 버전 관리 요구 사항  
 다음 데이터 서비스 구성이 동작하려면 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 프로토콜 버전 2 이상이 필요합니다.  
  
-   계산 요청 지원  
  
-   프로젝션의 $select 쿼리 옵션 지원  
  
 자세한 내용은 [데이터 서비스 버전 관리](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)을 참조하세요.  
  
## 참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [데이터 서비스 호스팅](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)