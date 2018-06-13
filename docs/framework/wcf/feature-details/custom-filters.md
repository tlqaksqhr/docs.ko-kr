---
title: 사용자 지정 필터
ms.date: 03/30/2017
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
ms.openlocfilehash: 4140a944ed195e1defc1a0677d8e26ff4ff85beb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489757"
---
# <a name="custom-filters"></a><span data-ttu-id="a0afd-102">사용자 지정 필터</span><span class="sxs-lookup"><span data-stu-id="a0afd-102">Custom Filters</span></span>
<span data-ttu-id="a0afd-103">사용자 지정 필터를 사용하면 시스템 제공 메시지 필터를 사용하여 정의할 수 없는 일치 논리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="a0afd-104">예를 들어 특정 메시지 요소를 해시한 다음 값을 검사하여 필터가 true를 반환하는지 아니면 false를 반환하는지를 확인하는 사용자 지정 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="a0afd-105">구현</span><span class="sxs-lookup"><span data-stu-id="a0afd-105">Implementation</span></span>  
 <span data-ttu-id="a0afd-106">사용자 지정 필터는 <xref:System.ServiceModel.Dispatcher.MessageFilter> 추상 기본 클래스의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="a0afd-107">사용자 지정 필터를 구현하는 경우 생성자가 단일 문자열 매개 변수를 필요에 따라 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="a0afd-108">이 매개 변수에는 런타임에 필터가 일치를 수행하는 데 필요한 값이나 구성을 제공하기 위해 MessageFilter 생성자에게 전달되는 구성 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="a0afd-109">예를 들어 이 정보를 사용하여 평가할 메시지 내에서 필터가 검색하는 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="a0afd-110">다음 예제에서는 문자열 매개 변수를 허용하는 사용자 지정 메시지 필터의 기본 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="a0afd-111">실제 구현에서는 match이 메시지 필터가 반환 해야 하는 경우를 확인 하는 메시지를 검사 하는 논리를 포함 **true** 또는 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="a0afd-112">성능</span><span class="sxs-lookup"><span data-stu-id="a0afd-112">Performance</span></span>  
 <span data-ttu-id="a0afd-113">사용자 지정 필터를 구현하는 경우에는 필터에서 메시지 평가를 완료하는 데 필요한 최대 시간을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="a0afd-114">메시지는 일치 항목을 찾을 때까지 여러 필터에 대해 평가될 수 있으므로 모든 필터가 평가되기 전에 클라이언트 요청이 시간 초과되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="a0afd-115">따라서 메시지가 필터 조건과 일치하는지 확인하려면 메시지의 내용 또는 특성을 평가하는 데 필요한 코드만 사용자 지정 필터에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="a0afd-116">일반적으로 사용자 지정 필터를 구현할 때는 다음 사항을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
-   <span data-ttu-id="a0afd-117">IO(예: 디스크 또는 데이터베이스에 데이터 저장)</span><span class="sxs-lookup"><span data-stu-id="a0afd-117">IO, such as saving data to disk or to a database.</span></span>  
  
-   <span data-ttu-id="a0afd-118">불필요한 처리(예: 문서의 여러 레코드 반복)</span><span class="sxs-lookup"><span data-stu-id="a0afd-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
-   <span data-ttu-id="a0afd-119">차단 작업(예: 공유 리소스에 대한 잠금 확보 또는 데이터베이스에 대한 조회 수행이 필요한 호출)</span><span class="sxs-lookup"><span data-stu-id="a0afd-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="a0afd-120">프로덕션 환경에서 사용자 지정 필터를 사용하기 전에 성능 테스트를 실행하여 필터에서 메시지를 평가하는 데 소요되는 평균 시간을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="a0afd-121">필터 테이블에 사용되는 다른 필터의 평균 처리 시간을 조합하면 클라이언트 응용 프로그램에서 지정하는 최대 제한 시간 값을 정확하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="a0afd-122">사용법</span><span class="sxs-lookup"><span data-stu-id="a0afd-122">Usage</span></span>  
 <span data-ttu-id="a0afd-123">사용자 지정 필터에서 라우팅 서비스를 사용 하기 위해 추가 해야를 필터 테이블 형식의 새 필터 항목을 지정 하 여 "Custom" 메시지 필터의 정규화 된 형식 이름 및 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="a0afd-124">다른 MessageFilter와 마찬가지로 사용자 지정 필터의 생성자에게 전달될 filterData 문자열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="a0afd-125">다음 예제에서는 라우팅 서비스에서 사용자 지정 필터를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0afd-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"   
            customType="CustomAssembly.MyMessageFilter,   
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```
