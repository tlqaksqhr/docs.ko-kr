---
title: '&lt;protocolMapping&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 769ca7b96c3671fdd1b154c99516778f7cbd542e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="14d39-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="14d39-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="14d39-103">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="14d39-104">런타임에 기본 끝점을 만들 때 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 구성된 매핑을 확인하여 특정 기본 주소에 사용할 바인딩을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-104">When creating default endpoints at runtime, [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="14d39-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="14d39-105">\<system.serviceModel></span></span>  
<span data-ttu-id="14d39-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="14d39-106">\<protocolMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d39-107">구문</span><span class="sxs-lookup"><span data-stu-id="14d39-107">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="14d39-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14d39-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14d39-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14d39-110">특성</span><span class="sxs-lookup"><span data-stu-id="14d39-110">Attributes</span></span>  
 <span data-ttu-id="14d39-111">없음</span><span class="sxs-lookup"><span data-stu-id="14d39-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14d39-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14d39-112">Child Elements</span></span>  
  
|<span data-ttu-id="14d39-113">요소</span><span class="sxs-lookup"><span data-stu-id="14d39-113">Element</span></span>|<span data-ttu-id="14d39-114">설명</span><span class="sxs-lookup"><span data-stu-id="14d39-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14d39-115">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="14d39-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="14d39-116">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14d39-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14d39-117">Parent Elements</span></span>  
  
|<span data-ttu-id="14d39-118">요소</span><span class="sxs-lookup"><span data-stu-id="14d39-118">Element</span></span>|<span data-ttu-id="14d39-119">설명</span><span class="sxs-lookup"><span data-stu-id="14d39-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14d39-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="14d39-120">system.ServiceModel</span></span>|<span data-ttu-id="14d39-121">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14d39-122">예제</span><span class="sxs-lookup"><span data-stu-id="14d39-122">Example</span></span>  
 <span data-ttu-id="14d39-123">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="14d39-124">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="14d39-125">또는 응용 프로그램 범위 내에서 기본 매핑을 재정의하려는 경우 해당 응용 프로그램 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14d39-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14d39-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14d39-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
