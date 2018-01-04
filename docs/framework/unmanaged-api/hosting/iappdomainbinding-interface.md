---
title: "IAppDomainBinding 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainBinding
api_location: mscoree.dll
api_type: COM
f1_keywords: IAppDomainBinding
helpviewer_keywords: IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a6f26c8337f89d829f42e00a9e5e79731a15156
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="654c2-102">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="654c2-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="654c2-103">공용 언어 런타임 (CLR) 응용 프로그램 도메인을 이미 만들었다고 호스트 응용 프로그램에 알리기 위해 호출 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="654c2-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="654c2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="654c2-104">Methods</span></span>  
  
|<span data-ttu-id="654c2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="654c2-105">Method</span></span>|<span data-ttu-id="654c2-106">설명</span><span class="sxs-lookup"><span data-stu-id="654c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="654c2-107">OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="654c2-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="654c2-108">공용 언어 런타임 (CLR)는 응용 프로그램 도메인이 생성 된 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="654c2-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="654c2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="654c2-109">Requirements</span></span>  
 <span data-ttu-id="654c2-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="654c2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="654c2-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="654c2-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="654c2-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="654c2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="654c2-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="654c2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654c2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="654c2-114">See Also</span></span>  
 [<span data-ttu-id="654c2-115">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="654c2-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
