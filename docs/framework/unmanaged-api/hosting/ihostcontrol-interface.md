---
title: "IHostControl 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e72ad562a73faf5682204c2ae2583b71cb3c05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="5eca7-102">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eca7-102">IHostControl Interface</span></span>
<span data-ttu-id="5eca7-103">어셈블리 로드를 구성 하 고 호스팅 인터페이스를 호스트에서 지원할 결정 하기 위한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eca7-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5eca7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5eca7-104">Methods</span></span>  
  
|<span data-ttu-id="5eca7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5eca7-105">Method</span></span>|<span data-ttu-id="5eca7-106">설명</span><span class="sxs-lookup"><span data-stu-id="5eca7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5eca7-107">GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="5eca7-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="5eca7-108">지정 된 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID`합니다.</span><span class="sxs-lookup"><span data-stu-id="5eca7-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="5eca7-109">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="5eca7-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="5eca7-110">응용 프로그램 도메인을 이미 만들었다고 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5eca7-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5eca7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5eca7-111">Requirements</span></span>  
 <span data-ttu-id="5eca7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5eca7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eca7-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5eca7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5eca7-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5eca7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5eca7-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eca7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eca7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eca7-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="5eca7-117">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eca7-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="5eca7-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eca7-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="5eca7-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eca7-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)