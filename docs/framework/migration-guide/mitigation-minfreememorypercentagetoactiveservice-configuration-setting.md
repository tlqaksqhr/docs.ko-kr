---
title: "완화: minFreeMemoryPercentageToActiveService 구성 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a><span data-ttu-id="21bac-102">완화: minFreeMemoryPercentageToActiveService 구성 설정</span><span class="sxs-lookup"><span data-stu-id="21bac-102">Mitigation: minFreeMemoryPercentageToActiveService Configuration Setting</span></span>
<span data-ttu-id="21bac-103">[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서는 웹 서버의 사용 가능한 메모리가 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 구성 설정에서 지정된 백분율보다 적으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-103">In the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], an exception is thrown if the available memory on the web server is less than the percentage specified by the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) configuration setting.</span></span> <span data-ttu-id="21bac-104">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이 설정이 무시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-104">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], this setting was ignored.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="21bac-105">영향</span><span class="sxs-lookup"><span data-stu-id="21bac-105">Impact</span></span>  
 <span data-ttu-id="21bac-106">대부분의 경우 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 관찰하는 것이 좋습니다. 제한된 메모리가 있는 시스템에서 WCF(Windows Communication Foundation) 서비스를 시작할 때 발생할 수 있는 <xref:System.OutOfMemoryException> 예외를 방지하여 시스템 안정성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-106">In most cases, the impact of observing the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting is desirable: It improves system stability by preventing the <xref:System.OutOfMemoryException> exceptions that can occur when a Windows Communication Foundation (WCF) service is started on a system that has constrained memory.</span></span>  
  
 <span data-ttu-id="21bac-107">그러나 이전에 성공적으로 시작된 서비스를 시작할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-107">However, in some cases, a service that previously started successfully may be unable to start.</span></span> <span data-ttu-id="21bac-108">이 경우 다음과 같은 자세한 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-108">In that case, a detailed error message appears:</span></span>  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a><span data-ttu-id="21bac-109">완화</span><span class="sxs-lookup"><span data-stu-id="21bac-109">Mitigation</span></span>  
 <span data-ttu-id="21bac-110">[minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 무시한 이전 동작으로 되돌리려면 web.config 파일을 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="21bac-110">To revert to the previous behavior where the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting was ignored, modify the web.config file as follows:</span></span>  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21bac-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21bac-111">See Also</span></span>  
 [<span data-ttu-id="21bac-112">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="21bac-112">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

