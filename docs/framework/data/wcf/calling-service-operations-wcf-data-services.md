---
title: "서비스 작업 호출(WCF Data Services)"
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
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e43fbe2002c19b8203ff048b4200dcfaad27afe0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="calling-service-operations-wcf-data-services"></a>서비스 작업 호출(WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]은 데이터 서비스에 대한 서비스 작업을 정의합니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서는 데이터 서비스에 메서드로 그러한 작업을 정의할 수 있습니다. 다른 데이터 서비스 리소스와 마찬가지로, 이러한 서비스 작업도 URI를 사용하여 지정합니다. 서비스 작업은 엔터티 형식의 컬렉션, 단일 엔터티 형식 인스턴스, 그리고 정수, 문자열과 같은 기본 형식을 반환할 수 있습니다. 서비스 작업은 `null`(Visual basic에서 `Nothing`)도 반환할 수 있습니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리는 HTTP GET 요청을 지원하는 서비스 작업에 액세스하는 데 사용할 수 있습니다. 이러한 종류의 서비스 작업은 <xref:System.ServiceModel.Web.WebGetAttribute>가 적용된 메서드로 정의할 수 있습니다. 자세한 내용은 참조 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)합니다.  
  
 서비스 작업은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]를 구현하는 데이터 서비스에서 반환하는 메타데이터에 노출됩니다. 메타데이터에서 서비스 작업은 `FunctionImport` 요소로 표현됩니다. 강력한 형식의 <xref:System.Data.Services.Client.DataServiceContext>를 생성할 경우 서비스 참조 추가 및 DataSvcUtil.exe 도구는 이 요소를 무시합니다. 이 때문에 서비스 작업을 직접 호출하는 데 사용할 수 있는 컨텍스트에서 메서드를 찾을 수 없습니다. 그러나, 다음 두 가지 중 한 가지 방법으로 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트를 사용하여 서비스 작업을 호출할 수 있습니다.  
  
-   기타 매개 변수와 함께 서비스 작업의 URI를 제공하여 <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>에 <xref:System.Data.Services.Client.DataServiceContext> 메서드를 호출합니다. 이 메서드는 모든 GET 서비스 작업을 호출하는 데 사용합니다.  
  
-   <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>에서 <xref:System.Data.Services.Client.DataServiceContext> 메서드를 사용하여 <xref:System.Data.Services.Client.DataServiceQuery%601> 개체를 만듭니다. <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>를 호출하면 서비스 작업의 이름이 `entitySetName` 매개 변수에 제공됩니다. 이 메서드는 열거될 때 또는 <xref:System.Data.Services.Client.DataServiceQuery%601> 메서드가 호출될 때 서비스 작업을 호출하는 <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A> 개체를 반환합니다. 이 메서드는 컬렉션을 반환하는 GET 서비스 작업을 호출하는 데 사용합니다. <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드를 사용하면 단일 매개 변수를 제공할 수 있습니다. 이 메서드에서 반환한 <xref:System.Data.Services.Client.DataServiceQuery%601> 개체는 모든 쿼리 개체와 같이 추가 구성할 수 있습니다. 자세한 내용은 참조 [데이터 서비스 쿼리](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)합니다.  
  
## <a name="considerations-for-calling-service-operations"></a>서비스 작업 호출에 대한 고려 사항  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트를 사용하여 서비스 작업을 호출하는 경우 다음과 같은 사항을 고려해야 합니다.  
  
-   에 해당 하는 비동기 데이터 서비스를 비동기적으로 액세스 하는 경우 사용 해야 <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> 에 대 한 메서드 <xref:System.Data.Services.Client.DataServiceContext> 또는 <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 에 대 한 메서드 <xref:System.Data.Services.Client.DataServiceQuery%601>합니다.  
  
-   [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리는 기본 형식의 컬렉션을 반환하는 서비스 작업에서의 결과를 구체화할 수 없습니다.  
  
-   [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리는 POST 서비스 작업 호출을 지원하지 않습니다. HTTP POST에서 호출하는 서비스 작업은 <xref:System.ServiceModel.Web.WebInvokeAttribute> 매개 변수와 `Method="POST"`를 사용하여 정의합니다. HTTP POST 요청을 사용하여 서비스 작업을 호출하려면 대신 <xref:System.Net.HttpWebRequest>를 사용해야 합니다.  
  
-   엔터티 또는 기본 형식의 단일 결과 또는 두 개 이상의 입력 매개 변수가 필요한 단일 결과를 반환하는 GET 서비스 작업을 호출하기 위해 <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>을 사용할 수 없습니다. 대신 <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> 메서드를 호출해야 합니다.  
  
-   도구에 의해 생성되고 <xref:System.Data.Services.Client.DataServiceContext> 또는 <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> 메서드를 사용하여 서비스 작업을 호출하는 강력한 형식의 <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> 부분 클래스에 확장 메서드를 만드는 것을 고려해 보세요. 이렇게 하면 컨텍스트에서 직접 서비스 작업을 호출할 수 있습니다. 자세한 내용은 블로그 게시물을 참조 하십시오. [서비스 작업 및 WCF Data Services 클라이언트](http://go.microsoft.com/fwlink/?LinkId=215668)합니다.  
  
-   <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>를 사용하여 서비스 작업을 호출하는 경우 클라이언트 라이브러리는 앰퍼샌드(&amp;)와 같은 예약 문자의 백분율 인코딩 및 문자열의 작은 따옴표 이스케이프를 수행하여 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>에 제공된 문자를 자동으로 이스케이프합니다. 그러나 호출 하는 경우 중 하나는 *Execute* 서비스 작업을 호출 하는 메서드를 반드시 모든 사용자가 제공한 문자열 값의 이스케이프 해야 합니다. URI의 작은 따옴표는 작은 따옴표의 쌍으로 이스케이프됩니다.  
  
## <a name="examples-of-calling-service-operations"></a>서비스 작업 호출 예제  
 이 단원에는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하여 서비스 작업을 호출하는 방법에 대한 다음 예제가 나와 있습니다.  
  
-   [U t e 호출&lt;T&gt; 엔터티 컬렉션을 반환 하려면](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
-   [CreateQuery를 사용 하 여&lt;T&gt; 엔터티 컬렉션을 반환 하려면](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
-   [U t e 호출&lt;T&gt; 단일 엔터티를 반환 하려면](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
-   [U t e 호출&lt;T&gt; 기본 값 컬렉션을 반환 하려면](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
-   [U t e 호출&lt;T&gt; 단일 기본 값을 반환 하려면](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
-   [서비스 작업을 호출 하는 데이터를 반환 하지](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
-   [서비스 작업을 비동기적으로 호출](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>   
### <a name="calling-executet-to-return-a-collection-of-entities"></a>U t e 호출\<T > 엔터티 컬렉션을 반환 하려면  
 다음 예제는 `city` 문자열 매개 변수를 사용하고 <xref:System.Linq.IQueryable%601>을 반환하는 GetOrdersByCity라는 서비스 작업을 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationiqueryable)]  
  
 이 예제에서는 서비스 작업이 관련 `Order` 개체를 사용하여 `Order_Detail` 개체의 컬렉션을 반환합니다.  
  
<a name="CreateQueryIQueryable"></a>   
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>CreateQuery를 사용 하 여\<T > 엔터티 컬렉션을 반환 하려면  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>를 사용하여 동일한 GetOrdersByCity 서비스 작업을 호출하는 데 사용되는 <xref:System.Data.Services.Client.DataServiceQuery%601>를 반환합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationcreatequery)]  
  
 이 예제에서 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드는 쿼리에 매개 변수를 추가하는 데 사용되고 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 메서드는 관련 Order_Details 개체를 결과에 포함하는 데 사용됩니다.  
  
<a name="ExecuteSingleEntity"></a>   
### <a name="calling-executet-to-return-a-single-entity"></a>U t e 호출\<T > 단일 엔터티를 반환 하려면  
 다음 예제에서는 단일 Order 엔터티만 반환하는 GetNewestOrder라는 서비스 작업을 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationsingleentity)]  
  
 이 예제에서 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 메서드는 실행 시 단일 Order 엔터티만 요청하는 데 사용됩니다.  
  
<a name="ExecutePrimitiveCollection"></a>   
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>U t e 호출\<T >의 기본 값 컬렉션을 반환 하려면  
 다음 예제에서는 문자열 값의 컬렉션을 반환하는 서비스 작업을 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>   
### <a name="calling-executet-to-return-a-single-primitive-value"></a>U t e 호출\<T > 단일 기본 값을 반환 하려면  
 다음 예제에서는 단일 문자열 값을 반환하는 서비스 작업을 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationsingleint)]  
  
 이 예제에서는 다시 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 메서드를 사용하여 실행 시 단일 정수 값만 요청합니다.  
  
<a name="ExecuteVoid"></a>   
### <a name="calling-a-service-operation-that-returns-no-data"></a>데이터를 반환하지 않는 서비스 작업 호출  
 다음 예제에서는 데이터를 반환하지 않는 서비스 작업을 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationvoid)]  
  
 데이터가 반환되지 않기 때문에 실행 값이 할당되지 않습니다. 요청이 성공했다는 유일한 표시는 <xref:System.Data.Services.Client.DataServiceQueryException>이 발생하지 않는다는 것입니다.  
  
<a name="ExecuteAsync"></a>   
### <a name="calling-a-service-operation-asynchronously"></a>서비스 작업을 비동기적으로 호출  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> 및 <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>를 호출하여 서비스 작업을 비동기적으로 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onasyncexecutioncomplete)]  
  
 데이터가 반환되지 않기 때문에 실행으로 반환된 값이 할당되지 않습니다. 요청이 성공했다는 유일한 표시는 <xref:System.Data.Services.Client.DataServiceQueryException>이 발생하지 않는다는 것입니다.  
  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>를 사용하여 동일한 서비스 작업을 비동기적으로 호출합니다.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
