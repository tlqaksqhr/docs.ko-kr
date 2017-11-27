---
title: "ICorConfiguration::SetGCHostControl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33d01ff208e9814e73c7a658e41819348da6831a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="77f1f-102">ICorConfiguration::SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="77f1f-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="77f1f-103">콜백 인터페이스를 호스트에 가상 메모리의 한계를 변경 하도록 요청 하는 가비지 수집기에서 사용할 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f1f-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="77f1f-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77f1f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77f1f-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="77f1f-106">[in] 에 대 한 포인터는 [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) 호스트에 가상 메모리의 한계를 변경 하도록 요청 하기 위해 가비지 수집기를 사용할 수 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="77f1f-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f1f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77f1f-107">Requirements</span></span>  
 <span data-ttu-id="77f1f-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77f1f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f1f-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77f1f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77f1f-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="77f1f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77f1f-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f1f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f1f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77f1f-112">See Also</span></span>  
 [<span data-ttu-id="77f1f-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77f1f-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
