---
title: DiscoveryClient 및 DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: d9bf5bf0032a299589292e51ad9bc273c56ced3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494468"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="c9cc9-102">DiscoveryClient 및 DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="c9cc9-102">DiscoveryClient and DynamicEndpoint</span></span>
<span data-ttu-id="c9cc9-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> 및 <xref:System.ServiceModel.Discovery.DynamicEndpoint>는 클라이언트 측에서 서비스를 검색하는 데 사용되는 두 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="c9cc9-104"><xref:System.ServiceModel.Discovery.DiscoveryClient>는 특정 조건 집합과 일치하는 서비스 목록을 제공하며 이를 통해 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="c9cc9-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint>는 동일한 작업을 수행하는 것 이외에도 검색된 서비스 중 하나에 자동으로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="c9cc9-106">모든 끝점을 <xref:System.ServiceModel.Discovery.DynamicEndpoint>로 만들 수 있고 구성을 통해 검색 조건을 추가할 수 있으므로 <xref:System.ServiceModel.Discovery.DynamicEndpoint>는 솔루션에서 검색을 수행해야 하지만 클라이언트 논리는 수정하지 않으려는 경우, 즉 끝점만 수정해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-106">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="c9cc9-107">반면에 <xref:System.ServiceModel.Discovery.DiscoveryClient>는 검색 작업을 보다 세부적으로 제어하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="c9cc9-108">각 클래스의 사용 방법과 이점은 아래에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-108">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="c9cc9-109">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="c9cc9-109">DiscoveryClient</span></span>  
 <span data-ttu-id="c9cc9-110"><xref:System.ServiceModel.Discovery.DiscoveryClient>는 동기 및 비동기 Find 메서드와 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 및 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트를 정의하며,</span><span class="sxs-lookup"><span data-stu-id="c9cc9-110">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="c9cc9-111">동기 및 비동기 Resolve 메서드와 <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> 이벤트도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-111">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="c9cc9-112"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 또는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> 메서드를 사용하면 서비스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-112">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="c9cc9-113">두 클래스는 모두 계약 형식 이름, 범위, 요청된 최대 결과 수 및 범위 일치 규칙을 지정할 수 있는 <xref:System.ServiceModel.Discovery.FindCriteria> 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-113">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="c9cc9-114"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 및 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> 메서드를 호출할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-114">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="c9cc9-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>가 서비스에서 응답을 수신할 때마다 <xref:System.ServiceModel.Discovery.DiscoveryClient>가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="c9cc9-116">이 이벤트는 찾기 작업의 진행률을 보여 주는 진행률 표시줄을 표시하는 데 사용할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="c9cc9-116">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="c9cc9-117">찾기 응답이 수신될 때 찾기 응답을 처리하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-117">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="c9cc9-118"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트는 찾기 작업이 완료될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-118">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="c9cc9-119">찾기 작업은 최대 응답 수에 도달했거나 <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>이 경과한 경우에 완료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-119">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="c9cc9-120">찾기 작업이 완료되면 <xref:System.ServiceModel.Discovery.FindResponse> 인스턴스에 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-120">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="c9cc9-121"><xref:System.ServiceModel.Discovery.FindResponse>에는 일치하는 서비스의 주소, 계약 형식 이름, 확장, 수신 대기 URI 및 범위가 들어 있는 <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>의 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-121">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="c9cc9-122">이 정보를 사용하면 일치하는 서비스 중 하나에 연결하고 이를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-122">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="c9cc9-123">다음 예제에서는 System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) 메서드를 호출 하 여 찾은 서비스를 호출 하려면 반환된 된 메타 데이터를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-123">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="c9cc9-124">사용 하는 이점은 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> 가 발견 한 하 고 나중에 사용 하 여 끝점의 목록을 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-124">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="c9cc9-125">이 캐시를 사용하면 사용자 지정 논리를 빌드하여 다양한 실패 조건을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-125">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
```  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine("No matching endpoints found");  
```  
  
 <span data-ttu-id="c9cc9-126">다음 예제에서는 찾기 작업을 비동기적으로 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-126">The following example shows how to perform a find operation asynchronously.</span></span>  
  
```  
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());   
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));   
}   
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}   
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{    
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
```  
  
 <span data-ttu-id="c9cc9-127">비동기 작업에 대 한 자세한 정보에 대 한 호출을 찾을, 참조 [비동기 찾기](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-127">For more information about making asynchronous find calls, see [Asynchronous Find](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md).</span></span>  
  
 <span data-ttu-id="c9cc9-128"><xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> 및 <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> 메서드를 사용하면 끝점 주소를 기반으로 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-128">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="c9cc9-129">이는 네트워크를 통해 끝점 주소에 액세스할 수 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-129">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="c9cc9-130">Resolve 메서드는 <xref:System.ServiceModel.Discovery.ResolveCriteria>의 인스턴스를 사용하므로 확인할 서비스의 끝점 주소, 확인 작업의 최대 기간 및 확장 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-130">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="c9cc9-131">다음 예제에서는 <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> 메서드를 사용하여 서비스를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-131">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="c9cc9-132">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="c9cc9-132">DynamicEndpoint</span></span>  
 <span data-ttu-id="c9cc9-133"><xref:System.ServiceModel.Discovery.DynamicEndpoint> 표준 끝점입니다 (자세한 내용은 참조 [표준 끝점](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) 검색을 수행 하 고 자동으로 일치 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-133"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="c9cc9-134">검색할 계약과 사용할 바인딩을 전달하여 <xref:System.ServiceModel.Discovery.DynamicEndpoint>를 만들고 <xref:System.ServiceModel.Discovery.DynamicEndpoint> 인스턴스를 WCF 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-134">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="c9cc9-135">다음 예제에서는 <xref:System.ServiceModel.Discovery.DynamicEndpoint>를 만들고 사용하여 계산기 서비스를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-135">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="c9cc9-136">검색은 클라이언트가 열릴 때마다 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-136">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="c9cc9-137">구성에 정의 된 끝점으로 변환할 수도 있습니다는 <xref:System.ServiceModel.Discovery.DynamicEndpoint> 추가 하 여는 `kind ="dynamicEndpoint"` 끝점 구성 요소에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc9-137">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
```  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9cc9-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9cc9-138">See Also</span></span>  
 [<span data-ttu-id="c9cc9-139">범위를 사용한 검색</span><span class="sxs-lookup"><span data-stu-id="c9cc9-139">Discovery with Scopes</span></span>](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)  
 [<span data-ttu-id="c9cc9-140">비동기 찾기</span><span class="sxs-lookup"><span data-stu-id="c9cc9-140">Asynchronous Find</span></span>](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md)  
 [<span data-ttu-id="c9cc9-141">기본</span><span class="sxs-lookup"><span data-stu-id="c9cc9-141">Basic</span></span>](../../../../docs/framework/wcf/samples/basic-sample.md)
