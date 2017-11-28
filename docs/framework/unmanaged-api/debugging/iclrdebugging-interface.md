---
title: "ICLRDebugging 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging
helpviewer_keywords: ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3e061b95faafeec3c3d233ab54f128a23c3264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="2cbe9-102">ICLRDebugging 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cbe9-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="2cbe9-103">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cbe9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2cbe9-104">Methods</span></span>  
  
|<span data-ttu-id="2cbe9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2cbe9-105">Method</span></span>|<span data-ttu-id="2cbe9-106">설명</span><span class="sxs-lookup"><span data-stu-id="2cbe9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cbe9-107">OpenVirtualProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="2cbe9-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="2cbe9-108">프로세스에서 로드 된 공용 언어 런타임 (CLR) 모듈에 해당 하는 "ICorDebugProcess" 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="2cbe9-109">CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="2cbe9-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="2cbe9-110">제공 하는 라이브러리 여부를 확인 한 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 인터페이스 사용 되 고 또는 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cbe9-111">설명</span><span class="sxs-lookup"><span data-stu-id="2cbe9-111">Remarks</span></span>  
 <span data-ttu-id="2cbe9-112">인스턴스를 가져올 수는 `ICLRDebugging` 인터페이스를 사용 하 여는 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cbe9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cbe9-113">Requirements</span></span>  
 <span data-ttu-id="2cbe9-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cbe9-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cbe9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cbe9-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cbe9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cbe9-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbe9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbe9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cbe9-118">See Also</span></span>  
 [<span data-ttu-id="2cbe9-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cbe9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2cbe9-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="2cbe9-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
