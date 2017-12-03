---
title: "활성화를 위한 &lt;diagnostics&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="3fc07-102">활성화를 위한 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="3fc07-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="3fc07-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 수신기의 진단 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc07-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="3fc07-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="3fc07-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="3fc07-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="3fc07-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc07-106">구문</span><span class="sxs-lookup"><span data-stu-id="3fc07-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="3fc07-107">형식</span><span class="sxs-lookup"><span data-stu-id="3fc07-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fc07-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3fc07-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3fc07-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc07-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fc07-110">특성</span><span class="sxs-lookup"><span data-stu-id="3fc07-110">Attributes</span></span>  
  
|<span data-ttu-id="3fc07-111">특성</span><span class="sxs-lookup"><span data-stu-id="3fc07-111">Attribute</span></span>|<span data-ttu-id="3fc07-112">설명</span><span class="sxs-lookup"><span data-stu-id="3fc07-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="3fc07-113">진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc07-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fc07-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3fc07-114">Child Elements</span></span>  
 <span data-ttu-id="3fc07-115">없음</span><span class="sxs-lookup"><span data-stu-id="3fc07-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fc07-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3fc07-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3fc07-117">요소</span><span class="sxs-lookup"><span data-stu-id="3fc07-117">Element</span></span>|<span data-ttu-id="3fc07-118">설명</span><span class="sxs-lookup"><span data-stu-id="3fc07-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fc07-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="3fc07-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="3fc07-120">수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc07-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fc07-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fc07-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
