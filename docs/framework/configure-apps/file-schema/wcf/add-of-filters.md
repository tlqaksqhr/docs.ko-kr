---
title: '&lt;filters&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 2a26a94c01fdb04b8a9e2d381a28cc909bbdac8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="fa300-102">&lt;filters&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="fa300-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="fa300-103">로깅할 메시지 종류를 지정하는 XPath 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="fa300-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa300-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa300-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="fa300-105">\<diagnostic></span></span>  
<span data-ttu-id="fa300-106">\<메시지 로깅 ></span><span class="sxs-lookup"><span data-stu-id="fa300-106">\<messageLogging></span></span>  
<span data-ttu-id="fa300-107">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="fa300-107">\<filters></span></span>  
<span data-ttu-id="fa300-108">\<add></span><span class="sxs-lookup"><span data-stu-id="fa300-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa300-109">구문</span><span class="sxs-lookup"><span data-stu-id="fa300-109">Syntax</span></span>  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa300-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa300-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa300-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa300-112">특성</span><span class="sxs-lookup"><span data-stu-id="fa300-112">Attributes</span></span>  
  
|<span data-ttu-id="fa300-113">특성</span><span class="sxs-lookup"><span data-stu-id="fa300-113">Attribute</span></span>|<span data-ttu-id="fa300-114">설명</span><span class="sxs-lookup"><span data-stu-id="fa300-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa300-115">필터</span><span class="sxs-lookup"><span data-stu-id="fa300-115">filter</span></span>|<span data-ttu-id="fa300-116">XPath 1.0 식에서 정의하는 XML 문서에 대한 쿼리를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="fa300-117">자세한 내용은 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa300-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa300-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa300-118">Child Elements</span></span>  
 <span data-ttu-id="fa300-119">없음</span><span class="sxs-lookup"><span data-stu-id="fa300-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa300-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa300-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fa300-121">요소</span><span class="sxs-lookup"><span data-stu-id="fa300-121">Element</span></span>|<span data-ttu-id="fa300-122">설명</span><span class="sxs-lookup"><span data-stu-id="fa300-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa300-123">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="fa300-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="fa300-124">로깅할 메시지 종류를 제어하는 데 사용되는 XPath 필터 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa300-125">설명</span><span class="sxs-lookup"><span data-stu-id="fa300-125">Remarks</span></span>  
 <span data-ttu-id="fa300-126">필터는 전송 계층에서만 적용됩니다(`logMessagesAtTransportLevel` = `true`).</span><span class="sxs-lookup"><span data-stu-id="fa300-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="fa300-127">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="fa300-128">컬렉션에 필터를 추가하려면 `add` 키워드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fa300-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="fa300-129">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="fa300-130">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="fa300-131">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="fa300-132">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="fa300-133">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa300-134">예제</span><span class="sxs-lookup"><span data-stu-id="fa300-134">Example</span></span>  
 <span data-ttu-id="fa300-135">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fa300-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa300-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa300-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [<span data-ttu-id="fa300-137">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="fa300-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="fa300-138">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="fa300-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="fa300-139">\<메시지 로깅 ></span><span class="sxs-lookup"><span data-stu-id="fa300-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
