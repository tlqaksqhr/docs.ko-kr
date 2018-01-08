---
title: "WCF 웹 HTTP 서비스에 대한 캐싱 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 723f485ab45cbe127bfd337c2d428d38d5f27232
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="caching-support-for-wcf-web-http-services"></a><span data-ttu-id="21ea7-102">WCF 웹 HTTP 서비스에 대한 캐싱 지원</span><span class="sxs-lookup"><span data-stu-id="21ea7-102">Caching Support for WCF Web HTTP Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="21ea7-103">WCF 웹 HTTP 서비스에서 ASP.NET에서 이미 사용할 수 있는 선언적 캐싱 메커니즘을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-103"> enables you to use the declarative caching mechanism already available in ASP.NET in your WCF Web HTTP services.</span></span> <span data-ttu-id="21ea7-104">이렇게 하면 WCF 웹 HTTP 서비스 작업의 응답을 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-104">This allows you to cache responses from your WCF Web HTTP service operations.</span></span> <span data-ttu-id="21ea7-105">사용자가 캐시용으로 구성된 서비스에 HTTP GET을 보내면 ASP.NET이 캐시된 응답을 다시 보내고 서비스 메서드가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-105">When a user sends an HTTP GET to your service that is configured for caching, ASP.NET sends back the cached response and the service method is not called.</span></span> <span data-ttu-id="21ea7-106">캐시가 만료되면 다음에 사용자가 HTTP GET을 보낼 때 서비스 메서드가 호출되고 응답이 다시 한 번 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-106">When the cache expires, the next time a user sends an HTTP GET, your service method is called and the response is once again cached.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="21ea7-107">ASP.NET 캐싱 참조 [ASP.NET Caching 개요](http://go.microsoft.com/fwlink/?LinkId=152534)</span><span class="sxs-lookup"><span data-stu-id="21ea7-107"> ASP.NET caching, see [ASP.NET Caching Overview](http://go.microsoft.com/fwlink/?LinkId=152534)</span></span>  
  
## <a name="basic-web-http-service-caching"></a><span data-ttu-id="21ea7-108">기본 웹 HTTP 서비스 캐싱</span><span class="sxs-lookup"><span data-stu-id="21ea7-108">Basic Web HTTP Service Caching</span></span>  
 <span data-ttu-id="21ea7-109">웹 HTTP 서비스 캐싱을 사용하도록 설정하려면 먼저 서비스에 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>를 적용하여 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A>를 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> 또는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>로 설정하여 ASP.NET 호환성을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-109">To enable WEB HTTP service caching you must first enable ASP.NET compatibility by applying the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to the service setting <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> to <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> or <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="21ea7-110">에서는 캐시 프로필 이름을 지정할 수 있는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>라는 새로운 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-110"> introduces a new attribute called <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> that allows you to specify a cache profile name.</span></span> <span data-ttu-id="21ea7-111">이 특성은 서비스 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-111">This attribute is applied to a service operation.</span></span> <span data-ttu-id="21ea7-112">다음 예제에서는 서비스에 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>를 적용하여 ASP.NET 호환성을 사용하도록 설정하고 `GetCustomer` 작업을 캐시용으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-112">The following example applies the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to a service to enable ASP.NET compatibility and configures the `GetCustomer` operation for caching.</span></span> <span data-ttu-id="21ea7-113"><!--zz<xref:System.ServiceModel.Activation.AspNetCacheProfileAttribute>--> `System.ServiceModel.Activation.AspNetCacheProfileAttribute` 특성에 사용할 캐시 설정이 포함 된 캐시 프로필을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-113">The <!--zz<xref:System.ServiceModel.Activation.AspNetCacheProfileAttribute>--> `System.ServiceModel.Activation.AspNetCacheProfileAttribute` attribute specifies a cache profile that contains the cache settings to be used.</span></span>  
  
```csharp
[ServiceContract] 
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
 <span data-ttu-id="21ea7-114">다음 예제와 같이 Web.config 파일에서도 ASP.NET 호환성 모드를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-114">You must also turn on ASP.NET compatibility mode in the Web.config file as shown in the following example.</span></span>  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
>  <span data-ttu-id="21ea7-115">ASP.NET 호환성 모드가 사용되도록 설정되어 있지 않은 경우 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>를 사용하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-115">If ASP.NET compatibility mode is not turned on and the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is used an exception is thrown.</span></span>  
  
 <span data-ttu-id="21ea7-116"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>에 지정된 캐시 프로필 이름은 Web.config 구성 파일에 추가되는 캐시 프로필을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-116">The cache profile name specified by the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifies a cache profile that is added to your Web.config configuration file.</span></span> <span data-ttu-id="21ea7-117">캐시 프로필에 정의 되는 <`outputCacheSetting`> 다음 구성 예제에 표시 된 대로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-117">The cache profile is defined with in a <`outputCacheSetting`> element as shown in the following configuration example.</span></span>  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="21ea7-118">이 요소는 ASP.NET 응용 프로그램에서 사용할 수 있는 구성 요소와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-118">This is the same configuration element that is available to ASP.NET applications.</span></span> <span data-ttu-id="21ea7-119">ASP.NET 캐시 프로필에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 <xref:System.Web.Configuration.OutputCacheProfile>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21ea7-119">[!INCLUDE[crabout](../../../../includes/crabout-md.md)] ASP.NET cache profiles, see <xref:System.Web.Configuration.OutputCacheProfile>.</span></span> <span data-ttu-id="21ea7-120">웹 HTTP 서비스의 경우 캐시 프로필에서 가장 중요한 특성이 `cacheDuration` 및 `varyByParam`입니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-120">For Web HTTP services, the most important attributes in the cache profile are: `cacheDuration` and `varyByParam`.</span></span> <span data-ttu-id="21ea7-121">두 특성 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-121">Both of these attributes are required.</span></span> <span data-ttu-id="21ea7-122">`cacheDuration`은 응답이 캐시되어야 하는 기간(초)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-122">`cacheDuration` sets the amount of time a response should be cached in seconds.</span></span> <span data-ttu-id="21ea7-123">`varyByParam`에서는 응답을 캐시하는 데 사용하는 쿼리 문자열 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-123">`varyByParam` allows you to specify a query string parameter that is used to cache responses.</span></span> <span data-ttu-id="21ea7-124">여러 쿼리 문자열 매개 변수 값을 사용하여 수행한 모든 요청은 개별적으로 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-124">All requests made with different query string parameter values are cached separately.</span></span> <span data-ttu-id="21ea7-125">예를 들어 http://MyServer/MyHttpService/MyOperation?param=10을 초기 요청한 후 동일한 URI를 사용하여 수행한 이후의 모든 요청은 캐시 기간이 만료되지 않는 한 캐시된 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-125">For example, once an initial request is made to http://MyServer/MyHttpService/MyOperation?param=10 all subsequent requests made with the same URI would be returned the cached response (so long as the cache duration has not elapsed).</span></span> <span data-ttu-id="21ea7-126">동일하지만 쿼리 문자열 매개 변수 값이 다른 유사한 요청에 대한 응답은 개별적으로 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-126">Responses for a similar request that is the same but has a different value for the parameter query string parameter are cached separately.</span></span> <span data-ttu-id="21ea7-127">이 개별 캐시 동작을 사용하지 않으려면 `varyByParam`을 "none"으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-127">If you do not want this separate caching behavior, set `varyByParam` to "none".</span></span>  
  
## <a name="sql-cache-dependency"></a><span data-ttu-id="21ea7-128">SQL 캐시 종속성</span><span class="sxs-lookup"><span data-stu-id="21ea7-128">SQL Cache Dependency</span></span>  
 <span data-ttu-id="21ea7-129">웹 HTTP 서비스 응답도 SQL 캐시 종속성을 사용하여 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-129">Web HTTP service responses can also be cached with a SQL cache dependency.</span></span> <span data-ttu-id="21ea7-130">WCF 웹 HTTP 서비스에서 SQL 데이터베이스에 저장된 데이터를 사용하는 경우 이 서비스의 응답을 캐시하고 SQL 데이터베이스 테이블의 데이터가 변경되면 캐시된 응답을 무효화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-130">If your WCF Web HTTP service depends on data stored in a SQL database, you may want to cache the service's response and invalidate the cached response when data in the SQL database table changes.</span></span> <span data-ttu-id="21ea7-131">이 동작은 Web.config 파일에서 완전히 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-131">This behavior is configured completely within the Web.config file.</span></span> <span data-ttu-id="21ea7-132">연결 문자열을 정의 해야는 <`connectionStrings`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-132">You must first define a connection string in the <`connectionStrings`> element.</span></span>  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 <span data-ttu-id="21ea7-133">내에서 SQL 캐시 종속성을 사용 하도록 설정 해야 합니다는 <`caching`> 내에서 요소는 <`system.web`> 다음 구성 예제에 표시 된 대로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-133">Then you must enable SQL cache dependency within a <`caching`> element within the <`system.web`> element as shown in the following config example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="21ea7-134">여기서 SQL 캐시 종속성이 사용되도록 설정되었고 폴링 시간이 1000밀리초로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-134">Here SQL cache dependency is enabled and a polling time of 1000 milliseconds is set.</span></span> <span data-ttu-id="21ea7-135">폴링 시간이 만료될 때마다 데이터베이스 테이블이 업데이트되었는지 확인하는 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-135">Each time the polling time elapses the database table is checked for updates.</span></span> <span data-ttu-id="21ea7-136">변경 내용이 감지되면 캐시의 내용이 제거되고 다음에 서비스 작업이 호출될 때 새 응답이 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-136">If changes are detected the contents of the cache are removed and the next time the service operation is invoked a new response is cached.</span></span> <span data-ttu-id="21ea7-137">내에서 <`sqlCacheDependency`> 요소는 데이터베이스를 추가 하 고 연결 문자열 내에서 참조는 <`databases`> 요소는 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-137">Within the <`sqlCacheDependency`> element add the databases and reference the connection strings within the <`databases`> element as shown in the following example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="21ea7-138">내에서 출력 캐시 설정을 구성 해야 하는 다음의 <`caching`> 요소는 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-138">Next you must configure the output cache settings within the <`caching`> element as shown in the following example.</span></span>  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="21ea7-139">여기서 캐시 기간이 60초로 설정되었고, `varyByParam`이 none으로 설정되었으며, `sqlDependency`가 콜론으로 구분된 데이터베이스/테이블 쌍의 세미콜론으로 구분된 목록으로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-139">Here the cache duration is set to 60 seconds, `varyByParam` is set to none and `sqlDependency` is set to a semicolon delimited list of database name/table pairs separated by colons.</span></span> <span data-ttu-id="21ea7-140">`MyTable`의 데이터가 변경되면 서비스 작업의 캐시된 응답이 제거되고, 서비스 작업이 호출되면 새 응답이 생성 및 캐시된 후 클라이언트에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-140">When data in `MyTable` is changed the cached response for the service operation is removed and when the operation is invoked a new response is generated (by calling the service operation), cached, and returned to the client.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="21ea7-141">SQL 데이터베이스에 액세스 하려면 ASP.NET을 사용 해야 합니다는 [ASP.NET SQL Server 등록 도구](http://go.microsoft.com/fwlink/?LinkId=152536)합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-141">For ASP.NET to access a SQL database, you must use the [ASP.NET SQL Server Registration Tool](http://go.microsoft.com/fwlink/?LinkId=152536).</span></span> <span data-ttu-id="21ea7-142">또한 적절한 사용자 계정을 사용하여 데이터베이스와 테이블에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-142">In addition you must allow the appropriate user account access to the database and table.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="21ea7-143">[웹 응용 프로그램에서 SQL Server에 액세스](http://go.microsoft.com/fwlink/?LinkId=178988)합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-143"> [Accessing SQL Server from a Web Application](http://go.microsoft.com/fwlink/?LinkId=178988).</span></span>  
  
## <a name="conditional-http-get-based-caching"></a><span data-ttu-id="21ea7-144">조건부 HTTP GET 기반 캐싱</span><span class="sxs-lookup"><span data-stu-id="21ea7-144">Conditional HTTP GET Based Caching</span></span>  
 <span data-ttu-id="21ea7-145">웹 HTTP 시나리오에서 조건부 HTTP GET 일반적으로 사용 서비스에 설명 된 대로 지능형 HTTP 캐싱을 구현 하는 [HTTP 사양](http://go.microsoft.com/fwlink/?LinkId=165800)합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-145">In Web HTTP scenarios a conditional HTTP GET is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](http://go.microsoft.com/fwlink/?LinkId=165800).</span></span> <span data-ttu-id="21ea7-146">서비스에서 지능형 HTTP 캐싱을 구현하려면 HTTP 응답에 있는 ETag 헤더의 값을 설정하고</span><span class="sxs-lookup"><span data-stu-id="21ea7-146">To do this the service must set the value of the ETag header in the HTTP response.</span></span> <span data-ttu-id="21ea7-147">HTTP 요청에 있는 If-None-Match 헤더를 검사하여 지정된 ETag가 현재 ETag와 일치하는지 여부도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-147">It also must check the If-None-Match header in the HTTP request to see whether any of the ETag specified matches the current ETag.</span></span>  
  
 <span data-ttu-id="21ea7-148">GET 및 HEAD 요청의 경우 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>는 ETag 값을 가져와서 요청의 If-None-Match 헤더와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-148">For GET and HEAD requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> takes an ETag value and checks it against the If-None-Match header of the request.</span></span> <span data-ttu-id="21ea7-149">이 헤더가 있고 ETag 값과 일치하면 HTTP 상태 코드 304(수정 안 됨)와 함께 <xref:System.ServiceModel.Web.WebFaultException>이 throw되고 일치하는 ETag가 있는 응답에 ETag 헤더가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-149">If the header is present and there is a match, a <xref:System.ServiceModel.Web.WebFaultException> with a HTTP status code 304 (Not Modified) is thrown and an ETag header is added to the response with the matching ETag.</span></span>  
  
 <span data-ttu-id="21ea7-150"><xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 메서드의 한 오버로드는 마지막으로 수정한 날짜를 가져와서 요청의 If-Modified-Since 헤더와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-150">One overload of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method takes a last modified date and checks it against the If-Modified-Since header of the request.</span></span> <span data-ttu-id="21ea7-151">이 헤더가 있고 리소스가 수정되지 않은 경우 HTTP 상태 코드 304(수정 안 됨)와 함께 <xref:System.ServiceModel.Web.WebFaultException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-151">If the header is present and the resource has not been modified since, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown.</span></span>  
  
 <span data-ttu-id="21ea7-152">PUT, POST 및 DELETE 요청의 경우 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>는 리소스의 현재 ETag 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-152">For PUT, POST, and DELETE requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> takes the current ETag value of a resource.</span></span> <span data-ttu-id="21ea7-153">메서드는 None-If-match 헤더의 값을 갖도록 확인 현재 ETag 값이 null 이면 "*"입니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-153">If the current ETag value is null, the method checks that the If-None- Match header has a value of "*".</span></span>  <span data-ttu-id="21ea7-154">현재 ETag 값이 기본값이 아니면 이 메서드는 현재 ETag 값을 요청의 If- Match 헤더와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-154">If the current ETag value is not a default value, then the method checks the current ETag value against the If- Match header of the request.</span></span> <span data-ttu-id="21ea7-155">두 경우 모두 예상 헤더가 요청에 없거나 해당 값이 조건부 검사를 충족하지 못하면 이 메서드는 HTTP 상태 코드 412(사전 조건 실패)와 함께 <xref:System.ServiceModel.Web.WebFaultException>을 throw하고 응답의 ETag 헤더를 현재 ETag 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-155">In either case, the method throws a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 412 (Precondition Failed) if the expected header is not present in the request or its value does not satisfy the conditional check and sets the ETag header of the response to the current ETag value.</span></span>  
  
 <span data-ttu-id="21ea7-156">`CheckConditional` 메서드와 <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> 메서드는 모두 HTTP 사양에 따라 응답 헤더에 설정된 ETag 값이 유효한 ETag인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-156">Both the `CheckConditional` methods and the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> method ensures that the ETag value set on the response header is a valid ETag according to the HTTP specification.</span></span> <span data-ttu-id="21ea7-157">여기에는 이러한 ETag 값이 아직 없고 내부 큰따옴표 문자로 올바로 이스케이프되지 않는 경우 큰따옴표로 이러한 값을 묶는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-157">This includes surrounding the ETag value in double quotes if they are not already present and properly escaping any internal double quote characters.</span></span> <span data-ttu-id="21ea7-158">약한 ETag 비교는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-158">Weak ETag comparison is not supported.</span></span>  
  
 <span data-ttu-id="21ea7-159">다음 예제에서는 이러한 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-159">The following example shows how to use these methods.</span></span>  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;
        
        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a><span data-ttu-id="21ea7-160">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="21ea7-160">Security Considerations</span></span>  
 <span data-ttu-id="21ea7-161">응답이 캐시에서 제공될 때는 권한 부여가 수행되지 않으므로 권한 부여가 필요한 요청의 경우 응답이 캐시되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-161">Requests that require authorization should not have their responses cached, because the authorization is not performed when the response is served from the cache.</span></span>  <span data-ttu-id="21ea7-162">이러한 응답을 캐시하면 보안이 심각하게 취약해집니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-162">Caching such responses would introduce a serious security vulnerability.</span></span>  <span data-ttu-id="21ea7-163">일반적으로 권한 부여가 필요한 요청에서는 사용자별 데이터를 제공하므로 서버 쪽 캐싱도 효과적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-163">Usually, requests that require authorization provide user-specific data and therefore server-side caching is not even beneficial.</span></span>  <span data-ttu-id="21ea7-164">이러한 경우 클라이언트 쪽 캐싱을 사용하거나 캐싱을 전혀 사용하지 않는 것이 더 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="21ea7-164">In such situations, client-side caching or simply not caching at all will be more appropriate.</span></span>
