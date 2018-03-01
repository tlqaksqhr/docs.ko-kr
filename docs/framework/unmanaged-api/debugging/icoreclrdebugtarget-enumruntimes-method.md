---
title: "ICoreClrDebugTarget::EnumRuntimes 메서드"
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
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a242d95785cf4421d30f716ac2987e42681aaef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="30ac1-102">ICoreClrDebugTarget::EnumRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="30ac1-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="30ac1-103">원격 컴퓨터에서 실행 중인 지정된 프로세스의 CLR(공용 언어 런타임)을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ac1-104">구문</span><span class="sxs-lookup"><span data-stu-id="30ac1-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30ac1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30ac1-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="30ac1-106">[in] 런타임을 열거하려는 프로세스의 내부 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="30ac1-107">이 `m_dwInternalID` 해당 [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="30ac1-108">[out] `ppRuntimes`에 반환된 런타임 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="30ac1-109">이 값은 0일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="30ac1-110">[out] 배열을 [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) 원격 대상 프로세스에 로드 된 런타임을 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30ac1-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="30ac1-111">Return Value</span></span>  
 <span data-ttu-id="30ac1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="30ac1-112">S_OK</span></span>  
 <span data-ttu-id="30ac1-113">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="30ac1-113">Success.</span></span>  
  
 <span data-ttu-id="30ac1-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="30ac1-114">S_FALSE</span></span>  
 <span data-ttu-id="30ac1-115">`dwInternalProcessID`가 컴퓨터에서 실행 중인 프로세스와 일치하지 않습니다. 프로세스가 종료된 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="30ac1-116">`pcRuntimes` 및 `ppRuntimes`가 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="30ac1-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="30ac1-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="30ac1-118">`ppRuntimes`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="30ac1-119">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="30ac1-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="30ac1-120">기타 실패</span><span class="sxs-lookup"><span data-stu-id="30ac1-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ac1-121">설명</span><span class="sxs-lookup"><span data-stu-id="30ac1-121">Remarks</span></span>  
 <span data-ttu-id="30ac1-122">이 메서드에 의해 할당 된 메모리를 확보 하기 위해 호출 된 [icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="30ac1-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ac1-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30ac1-123">Requirements</span></span>  
 <span data-ttu-id="30ac1-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30ac1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ac1-125">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="30ac1-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="30ac1-126">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="30ac1-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="30ac1-127">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="30ac1-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ac1-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30ac1-128">See Also</span></span>  
 [<span data-ttu-id="30ac1-129">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30ac1-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
