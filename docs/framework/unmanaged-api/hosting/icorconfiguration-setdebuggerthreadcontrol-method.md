---
title: "ICorConfiguration::SetDebuggerThreadControl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 46bd2b7a40cbcf4f68b8c2f62fea466aa17f2d31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="ff11e-102">ICorConfiguration::SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="ff11e-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="ff11e-103">디버깅 서비스 디버깅을 위해 공용 언어 런타임 (CLR) 스레드를 차단 하 여 차단 해제를 호출 하는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff11e-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff11e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff11e-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff11e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff11e-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="ff11e-106">[in] 에 대 한 포인터는 [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) 개체를 차단 하 고 디버깅 서비스에 의해 스레드 차단을 해제 하는 방법에 대 한 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ff11e-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff11e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff11e-107">Requirements</span></span>  
 <span data-ttu-id="ff11e-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff11e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff11e-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff11e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff11e-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ff11e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff11e-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff11e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff11e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff11e-112">See Also</span></span>  
 [<span data-ttu-id="ff11e-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff11e-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
