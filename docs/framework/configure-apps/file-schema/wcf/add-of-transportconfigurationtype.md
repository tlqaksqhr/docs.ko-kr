---
title: "&lt;transportConfigurationType&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b52345ae30ab56a6f34d2aa46f9836d67555b15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="e8ebc-102">&lt;transportConfigurationType&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="e8ebc-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="e8ebc-103">이 요소는 특정 전송 형식을 식별하는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="e8ebc-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e8ebc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8ebc-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e8ebc-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="e8ebc-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e8ebc-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="e8ebc-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e8ebc-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ebc-108">구문</span><span class="sxs-lookup"><span data-stu-id="e8ebc-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8ebc-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8ebc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e8ebc-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8ebc-111">특성</span><span class="sxs-lookup"><span data-stu-id="e8ebc-111">Attributes</span></span>  
  
|<span data-ttu-id="e8ebc-112">특성</span><span class="sxs-lookup"><span data-stu-id="e8ebc-112">Attribute</span></span>|<span data-ttu-id="e8ebc-113">설명</span><span class="sxs-lookup"><span data-stu-id="e8ebc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8ebc-114">name</span><span class="sxs-lookup"><span data-stu-id="e8ebc-114">name</span></span>|<span data-ttu-id="e8ebc-115">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="e8ebc-116">전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="e8ebc-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e8ebc-117">transportConfigurationType</span></span>|<span data-ttu-id="e8ebc-118">특정 전송을 구현하는 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8ebc-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8ebc-119">Child Elements</span></span>  
 <span data-ttu-id="e8ebc-120">없음</span><span class="sxs-lookup"><span data-stu-id="e8ebc-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8ebc-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8ebc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e8ebc-122">요소</span><span class="sxs-lookup"><span data-stu-id="e8ebc-122">Element</span></span>|<span data-ttu-id="e8ebc-123">설명</span><span class="sxs-lookup"><span data-stu-id="e8ebc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8ebc-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e8ebc-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="e8ebc-125">특정 전송을 구현하는 형식의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e8ebc-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8ebc-126">예</span><span class="sxs-lookup"><span data-stu-id="e8ebc-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8ebc-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8ebc-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="e8ebc-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="e8ebc-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
