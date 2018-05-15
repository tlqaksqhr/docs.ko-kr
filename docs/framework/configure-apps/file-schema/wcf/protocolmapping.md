---
title: '&lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 4afdaaa62c1ac3241eb7382d0995bed51bde73e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="ff3a8-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="ff3a8-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="ff3a8-103">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="ff3a8-104">런타임에 기본 끝점을 만들 때 Windows Communication Foundation (WCF)에서는 구성 된 매핑을 확인 하 고 기본 주소에서 특정 작업에 대해 사용할 바인딩을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-104">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="ff3a8-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ff3a8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ff3a8-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="ff3a8-106">\<protocolMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3a8-107">구문</span><span class="sxs-lookup"><span data-stu-id="ff3a8-107">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff3a8-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ff3a8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff3a8-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff3a8-110">특성</span><span class="sxs-lookup"><span data-stu-id="ff3a8-110">Attributes</span></span>  
 <span data-ttu-id="ff3a8-111">없음</span><span class="sxs-lookup"><span data-stu-id="ff3a8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff3a8-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ff3a8-112">Child Elements</span></span>  
  
|<span data-ttu-id="ff3a8-113">요소</span><span class="sxs-lookup"><span data-stu-id="ff3a8-113">Element</span></span>|<span data-ttu-id="ff3a8-114">설명</span><span class="sxs-lookup"><span data-stu-id="ff3a8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff3a8-115">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="ff3a8-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="ff3a8-116">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff3a8-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ff3a8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ff3a8-118">요소</span><span class="sxs-lookup"><span data-stu-id="ff3a8-118">Element</span></span>|<span data-ttu-id="ff3a8-119">설명</span><span class="sxs-lookup"><span data-stu-id="ff3a8-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff3a8-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ff3a8-120">system.ServiceModel</span></span>|<span data-ttu-id="ff3a8-121">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff3a8-122">예제</span><span class="sxs-lookup"><span data-stu-id="ff3a8-122">Example</span></span>  
 <span data-ttu-id="ff3a8-123">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="ff3a8-124">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="ff3a8-125">또는 응용 프로그램 범위 내에서 기본 매핑을 재정의하려는 경우 해당 응용 프로그램 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff3a8-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff3a8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff3a8-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
