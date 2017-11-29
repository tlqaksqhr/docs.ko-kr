---
title: "서비스 작업(WCF Data Services)"
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
- service operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: 583a690a-e60f-4990-8991-d6efce069d76
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 43f2b4bf7a7617587d76252108ec1ab5fb194a11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-operations-wcf-data-services"></a><span data-ttu-id="b6184-102">서비스 작업(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b6184-102">Service Operations (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="b6184-103">를 사용하면 데이터 서비스에 서버의 메서드를 노출하는 서비스 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-103"> enables you to define service operations on a data service to expose methods on the server.</span></span> <span data-ttu-id="b6184-104">다른 데이터 서비스 리소스와 마찬가지로 서비스 작업도 URI로 주소가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-104">Like other data service resources, service operations are addressed by URIs.</span></span> <span data-ttu-id="b6184-105">서비스 작업을 사용하면 유효성 검사 논리 구현, 역할 기반 보안 적용 또는 특수 쿼리 기능 노출 등을 위해 데이터 서비스에 비즈니스 논리를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-105">Service operations enable you to expose business logic in a data service, such as to implement validation logic, to apply role-based security, or to expose specialized querying capabilities.</span></span> <span data-ttu-id="b6184-106">서비스 작업은 <xref:System.Data.Services.DataService%601>에서 파생되는 데이터 서비스 클래스에 추가된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-106">Service operations are methods added to the data service class that derives from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="b6184-107">다른 모든 데이터 서비스 리소스와 마찬가지로 서비스 작업 메서드에 매개 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-107">Like all other data service resources, you can supply parameters to the service operation method.</span></span> <span data-ttu-id="b6184-108">예를 들어, 다음 서비스 작업 URI (기반는 [퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) 데이터 서비스) 값을 전달 `London` 에 `city` 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="b6184-108">For example, the following service operation URI (based on the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) data service) passes the value `London` to the `city` parameter:</span></span>  
  
```  
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'  
```  
  
 <span data-ttu-id="b6184-109">이 서비스 작업의 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-109">The definition for this service operation is as follows:</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
 [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
 <span data-ttu-id="b6184-110"><xref:System.Data.Services.DataService%601.CurrentDataSource%2A>의 <xref:System.Data.Services.DataService%601>를 사용하여 데이터 서비스에서 사용하는 데이터 소스에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-110">You can use the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> of the <xref:System.Data.Services.DataService%601> to directly access the data source that the data service is using.</span></span> <span data-ttu-id="b6184-111">자세한 내용은 참조 [하는 방법: 서비스 작업 정의](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-111">For more information, see [How to: Define a Service Operation](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b6184-112">.NET Framework 클라이언트 응용 프로그램에서 서비스 작업을 호출 하는 방법에 대 한 정보를 참조 하십시오. [서비스 작업 호출](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-112">For information on how to call a service operation from a .NET Framework client application, see [Calling Service Operations](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md).</span></span>  
  
## <a name="service-operation-requirements"></a><span data-ttu-id="b6184-113">서비스 작업 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6184-113">Service Operation Requirements</span></span>  
 <span data-ttu-id="b6184-114">데이터 서비스에 서비스 작업을 정의할 때 적용되는 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-114">The following requirements apply when defining service operations on the data service.</span></span> <span data-ttu-id="b6184-115">이러한 요구 사항을 충족하지 않는 메서드는 데이터 서비스의 서비스 작업으로 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-115">If a method does not meet these requirements, it will not be exposed as a service operation for the data service.</span></span>  
  
-   <span data-ttu-id="b6184-116">작업은 데이터 서비스 클래스의 멤버인 공용 인스턴스 메서드여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-116">The operation must be a public instance method that is a member of the data service class.</span></span>  
  
-   <span data-ttu-id="b6184-117">작업 메서드는 입력 매개 변수만 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-117">The operation method may only accept input parameters.</span></span> <span data-ttu-id="b6184-118">메시지 본문에 전송되는 데이터는 데이터 서비스가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-118">Data sent in the message body cannot be accessed by the data service.</span></span>  
  
-   <span data-ttu-id="b6184-119">매개 변수를 정의할 때 각 매개 변수의 형식은 기본 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-119">If parameters are defined, the type of each parameter must be a primitive type.</span></span> <span data-ttu-id="b6184-120">기본이 아닌 형식의 모든 데이터는 serialize한 다음 문자열 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-120">Any data of a non-primitive type must be serialized and passed into a string parameter.</span></span>  
  
-   <span data-ttu-id="b6184-121">메서드는 다음 중 하나를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-121">The method must return one of the following:</span></span>  
  
    -   <span data-ttu-id="b6184-122">`void`(Visual Basic에서는 `Nothing`)</span><span class="sxs-lookup"><span data-stu-id="b6184-122">`void` (`Nothing` in Visual Basic)</span></span>  
  
    -   <xref:System.Collections.Generic.IEnumerable%601>  
  
    -   <xref:System.Linq.IQueryable%601>  
  
    -   <span data-ttu-id="b6184-123">데이터 서비스에서 노출하는 데이터 모델의 엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="b6184-123">An entity type in the data model that the data service exposes.</span></span>  
  
    -   <span data-ttu-id="b6184-124">정수 또는 문자열과 같은 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="b6184-124">A primitive class such as integer or string.</span></span>  
  
-   <span data-ttu-id="b6184-125">정렬, 페이징, 필터링 등의 쿼리 옵션을 지원할 수 있도록 서비스 작업 메서드가 <xref:System.Linq.IQueryable%601>를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-125">In order to support query options such as sorting, paging, and filtering, service operation methods should return <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="b6184-126"><xref:System.Collections.Generic.IEnumerable%601>만 반환하는 작업의 경우 쿼리 옵션을 포함하는 서비스 작업 요청이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-126">Requests to service operations that include query options are rejected for operations that only return <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
-   <span data-ttu-id="b6184-127">탐색 속성을 사용하여 관련 엔터티에 액세스할 수 있도록 지원하려면 서비스 작업이 <xref:System.Linq.IQueryable%601>을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-127">In order to support accessing related entities by using navigation properties, the service operation must return <xref:System.Linq.IQueryable%601>.</span></span>  
  
-   <span data-ttu-id="b6184-128">메서드에 `[WebGet]` 또는 `[WebInvoke]` 특성이 주석으로 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-128">The method must be annotated with the `[WebGet]` or `[WebInvoke]` attribute.</span></span>  
  
    -   <span data-ttu-id="b6184-129">`[WebGet]`을 사용하면 GET 요청을 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-129">`[WebGet]` enables the method to be invoked by using a GET request.</span></span>  
  
    -   <span data-ttu-id="b6184-130">`[WebInvoke(Method = "POST")]`을 사용하면 POST 요청을 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-130">`[WebInvoke(Method = "POST")]` enables the method to be invoked by using a POST request.</span></span> <span data-ttu-id="b6184-131">다른 <xref:System.ServiceModel.Web.WebInvokeAttribute> 메서드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-131">Other <xref:System.ServiceModel.Web.WebInvokeAttribute> methods are not supported.</span></span>  
  
-   <span data-ttu-id="b6184-132">메서드의 반환 값이 엔터티 컬렉션이 아니라 단일 엔터티가 되도록 지정하는 <xref:System.Data.Services.SingleResultAttribute>를 서비스 작업에 주석으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-132">A service operation may be annotated with the <xref:System.Data.Services.SingleResultAttribute> that specifies that the return value from the method is a single entity rather than a collection of entities.</span></span> <span data-ttu-id="b6184-133">이 특성은 응답의 결과 serialization과 추가 탐색 속성 통과가 URI에 표시되는 방식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-133">This distinction dictates the resulting serialization of the response and the manner in which additional navigation property traversals are represented in the URI.</span></span> <span data-ttu-id="b6184-134">예를 들어 AtomPub serialization을 사용할 경우 단일 리소스 형식 인스턴스는 entry 요소로 나타나고 인스턴스 집합은 feed 요소로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-134">For example, when using AtomPub serialization, a single resource type instance is represented as an entry element and a set of instances as a feed element.</span></span>  
  
## <a name="addressing-service-operations"></a><span data-ttu-id="b6184-135">서비스 작업 주소 지정</span><span class="sxs-lookup"><span data-stu-id="b6184-135">Addressing Service Operations</span></span>  
 <span data-ttu-id="b6184-136">URI의 첫 번째 경로 세그먼트에 메서드 이름을 배치하여 서비스 작업의 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-136">You can address service operations by placing the name of the method in the first path segment of a URI.</span></span> <span data-ttu-id="b6184-137">예를 들어 다음 URI는 `GetOrdersByState` 개체의 <xref:System.Linq.IQueryable%601> 컬렉션을 반환하는 `Orders` 작업에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-137">As an example, the following URI accesses a `GetOrdersByState` operation that returns an <xref:System.Linq.IQueryable%601> collection of `Orders` objects.</span></span>  
  
```  
http://localhost:12345/Northwind.svc/GetOrdersByState?state='CA'&includeItems=true  
```  
  
 <span data-ttu-id="b6184-138">서비스 작업을 호출할 때 매개 변수는 쿼리 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-138">When calling a service operation, parameters are supplied as query options.</span></span> <span data-ttu-id="b6184-139">이전 서비스 작업은 문자열 매개 변수 `state`와 관련 `includeItems` 개체를 응답에 포함해야 하는지 여부를 나타내는 부울 매개 변수 `Order_Detail` 둘 다를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-139">The previous service operation accepts both a string parameter `state` and a Boolean parameter `includeItems` that indicates whether to include related `Order_Detail` objects in the response.</span></span>  
  
 <span data-ttu-id="b6184-140">서비스 작업에 대해 유효한 반환 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-140">The following are valid return types for a service operation:</span></span>  
  
|<span data-ttu-id="b6184-141">유효한 반환 형식</span><span class="sxs-lookup"><span data-stu-id="b6184-141">Valid Return Types</span></span>|<span data-ttu-id="b6184-142">URI 규칙</span><span class="sxs-lookup"><span data-stu-id="b6184-142">URI Rules</span></span>|  
|------------------------|---------------|  
|<span data-ttu-id="b6184-143">`void`(Visual Basic에서는 `Nothing`)</span><span class="sxs-lookup"><span data-stu-id="b6184-143">`void` (`Nothing` in Visual Basic)</span></span><br /><br /> <span data-ttu-id="b6184-144">또는</span><span class="sxs-lookup"><span data-stu-id="b6184-144">-or-</span></span><br /><br /> <span data-ttu-id="b6184-145">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="b6184-145">Entity types</span></span><br /><br /> <span data-ttu-id="b6184-146">또는</span><span class="sxs-lookup"><span data-stu-id="b6184-146">-or-</span></span><br /><br /> <span data-ttu-id="b6184-147">기본 형식</span><span class="sxs-lookup"><span data-stu-id="b6184-147">Primitive types</span></span>|<span data-ttu-id="b6184-148">URI는 서비스 작업의 이름에 해당하는 단일 경로 세그먼트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-148">The URI must be a single path segment that is the name of the service operation.</span></span> <span data-ttu-id="b6184-149">쿼리 옵션은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-149">Query options are not allowed.</span></span>|  
|<xref:System.Collections.Generic.IEnumerable%601>|<span data-ttu-id="b6184-150">URI는 서비스 작업의 이름에 해당하는 단일 경로 세그먼트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-150">The URI must be a single path segment that is the name of the service operation.</span></span> <span data-ttu-id="b6184-151">결과 형식이 <xref:System.Linq.IQueryable%601> 형식이 아니므로 쿼리 옵션은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-151">Because the result type is not an <xref:System.Linq.IQueryable%601> type, query options are not allowed.</span></span>|  
|<xref:System.Linq.IQueryable%601>|<span data-ttu-id="b6184-152">서비스 작업의 이름에 해당하는 경로 외에도 쿼리 경로 세그먼트가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-152">Query path segments in addition to the path that is the name of the service operation are allowed.</span></span> <span data-ttu-id="b6184-153">쿼리 옵션도 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-153">Query options are also allowed.</span></span>|  
  
 <span data-ttu-id="b6184-154">서비스 작업의 반환 형식에 따라 추가 경로 세그먼트나 쿼리 옵션이 URI에 추가될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-154">Additional path segments or query options may be added to the URI depending on the return type of the service operation.</span></span> <span data-ttu-id="b6184-155">예를 들어 다음 URI는 관련 `GetOrdersByCity` 개체와 함께 <xref:System.Linq.IQueryable%601> 개체의 `Orders` 컬렉션을 `RequiredDate`의 내림차순으로 정렬하여 반환하는 `Order_Details` 작업에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-155">For example, the following URI accesses a `GetOrdersByCity` operation that returns an <xref:System.Linq.IQueryable%601> collection of `Orders` objects, ordered by `RequiredDate` in descending order, along with the related `Order_Details` objects:</span></span>  
  
```  
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc  
```  
  
## <a name="service-operations-access-control"></a><span data-ttu-id="b6184-156">서비스 작업 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b6184-156">Service Operations Access Control</span></span>  
 <span data-ttu-id="b6184-157">서비스 전반에 걸친 서비스 작업의 표시는 <xref:System.Data.Services.IDataServiceConfiguration.SetServiceOperationAccessRule%2A> 클래스의 <xref:System.Data.Services.IDataServiceConfiguration> 메서드에 의해 제어되며, 이는 엔터티 집합의 표시가 <xref:System.Data.Services.IDataServiceConfiguration.SetEntitySetAccessRule%2A> 메서드를 사용하여 제어되는 방식과 상당 부분 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-157">Service-wide visibility of service operations is controlled by the <xref:System.Data.Services.IDataServiceConfiguration.SetServiceOperationAccessRule%2A> method on the <xref:System.Data.Services.IDataServiceConfiguration> class in much the same way that entity set visibility is controlled by using the <xref:System.Data.Services.IDataServiceConfiguration.SetEntitySetAccessRule%2A> method.</span></span> <span data-ttu-id="b6184-158">예를 들어, 데이터 서비스 정의의 다음 코드 줄은 `CustomersByCity` 서비스 작업에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-158">For example, the following line of code in the data service definition enables access to the `CustomersByCity` service operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
 [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
> [!NOTE]
>  <span data-ttu-id="b6184-159">서비스 작업의 반환 형식이 기본 엔터티 집합에 대한 액세스를 제한하여 숨겨진 경우에는 클라이언트 응용 프로그램에서 서비스 작업을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-159">If a service operation has a return type that has been hidden by restricting access on the underlying entity sets, then the service operation will not be available to client applications.</span></span>  
  
 <span data-ttu-id="b6184-160">자세한 내용은 참조 [하는 방법: 서비스 작업 정의](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-160">For more information, see [How to: Define a Service Operation](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md).</span></span>  
  
## <a name="raising-exceptions"></a><span data-ttu-id="b6184-161">예외 발생</span><span class="sxs-lookup"><span data-stu-id="b6184-161">Raising Exceptions</span></span>  
 <span data-ttu-id="b6184-162">데이터 서비스 실행에서 예외를 발생시킬 때마다 <xref:System.Data.Services.DataServiceException> 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-162">We recommend that you use the <xref:System.Data.Services.DataServiceException> class whenever you raise an exception in the data service execution.</span></span> <span data-ttu-id="b6184-163">그 이유는 데이터 서비스 런타임이 이 예외 개체의 속성을 HTTP 응답 메시지에 올바르게 매핑하는 방법을 알기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-163">This is because the data service runtime knows how to map properties of this exception object correctly to the HTTP response message.</span></span> <span data-ttu-id="b6184-164">서비스 작업에서 <xref:System.Data.Services.DataServiceException>을 발생시키면 반환된 예외가 <xref:System.Reflection.TargetInvocationException>으로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-164">When you raise a <xref:System.Data.Services.DataServiceException> in a service operation, the returned exception is wrapped in a <xref:System.Reflection.TargetInvocationException>.</span></span> <span data-ttu-id="b6184-165"><xref:System.Data.Services.DataServiceException>을 묶지 않고 기본 <xref:System.Reflection.TargetInvocationException>을 반환하려면 다음 예제와 같이 <xref:System.Data.Services.DataService%601.HandleException%2A>에 <xref:System.Data.Services.DataService%601> 메서드를 재정의하고 <xref:System.Data.Services.DataServiceException>에서 <xref:System.Reflection.TargetInvocationException>을 추출해서 최상위 오류로 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6184-165">To return the base <xref:System.Data.Services.DataServiceException> without the enclosing <xref:System.Reflection.TargetInvocationException>, you must override the <xref:System.Data.Services.DataService%601.HandleException%2A> method in the <xref:System.Data.Services.DataService%601>, extract the <xref:System.Data.Services.DataServiceException> from the <xref:System.Reflection.TargetInvocationException>, and return it as the top-level error, as in the following example:</span></span>  
  
 [!code-csharp[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#handleexceptions)]
 [!code-vb[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#handleexceptions)]  
  
## <a name="see-also"></a><span data-ttu-id="b6184-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6184-166">See Also</span></span>  
 [<span data-ttu-id="b6184-167">인터셉터</span><span class="sxs-lookup"><span data-stu-id="b6184-167">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)
