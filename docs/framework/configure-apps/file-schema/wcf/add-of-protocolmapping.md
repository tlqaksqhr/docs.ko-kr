---
title: "&lt;protocolMapping&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 255cd8518bd9c6c6c199c75aa32ca086c801d23f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="a8ce7-102">&lt;protocolMapping&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="a8ce7-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="a8ce7-103">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 간의 기본 프로토콜 매핑을 나타냅니다 및 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 바인딩.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] binding.</span></span> <span data-ttu-id="a8ce7-104">런타임에 기본 끝점을 만들 때 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 구성된 매핑을 확인하여 특정 기본 주소에 사용할 바인딩을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-104">When creating default endpoints at runtime, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="a8ce7-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a8ce7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a8ce7-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="a8ce7-106">\<protocolMapping></span></span>  
<span data-ttu-id="a8ce7-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a8ce7-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ce7-108">구문</span><span class="sxs-lookup"><span data-stu-id="a8ce7-108">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8ce7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a8ce7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a8ce7-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8ce7-111">특성</span><span class="sxs-lookup"><span data-stu-id="a8ce7-111">Attributes</span></span>  
  
|<span data-ttu-id="a8ce7-112">요소</span><span class="sxs-lookup"><span data-stu-id="a8ce7-112">Element</span></span>|<span data-ttu-id="a8ce7-113">설명</span><span class="sxs-lookup"><span data-stu-id="a8ce7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8ce7-114">바인딩</span><span class="sxs-lookup"><span data-stu-id="a8ce7-114">binding</span></span>|<span data-ttu-id="a8ce7-115">기본 끝점을 만드는 중에 끝점으로 사용할 바인딩 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="a8ce7-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8ce7-116">bindingConfiguration</span></span>|<span data-ttu-id="a8ce7-117">참조할 바인딩 구성 섹션의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="a8ce7-118">scheme</span><span class="sxs-lookup"><span data-stu-id="a8ce7-118">scheme</span></span>|<span data-ttu-id="a8ce7-119">기본 끝점으로 사용될 전송 프로토콜 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8ce7-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a8ce7-120">Child Elements</span></span>  
 <span data-ttu-id="a8ce7-121">없음</span><span class="sxs-lookup"><span data-stu-id="a8ce7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8ce7-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a8ce7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a8ce7-123">요소</span><span class="sxs-lookup"><span data-stu-id="a8ce7-123">Element</span></span>|<span data-ttu-id="a8ce7-124">설명</span><span class="sxs-lookup"><span data-stu-id="a8ce7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8ce7-125">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="a8ce7-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="a8ce7-126">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 간의 기본 프로토콜 매핑을 정의 하기 위한 구성 섹션을 나타냅니다 및 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 바인딩.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a8ce7-127">예제</span><span class="sxs-lookup"><span data-stu-id="a8ce7-127">Example</span></span>  
 <span data-ttu-id="a8ce7-128">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="a8ce7-129">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="a8ce7-130">또는 응용 프로그램 범위 내에서 기본 매핑을 재정의하려는 경우 해당 응용 프로그램 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ce7-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8ce7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8ce7-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
