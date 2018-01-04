---
title: "ICoreClrDebugTarget::EnumProcesses 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumProcesses
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8296b4b137032400ee172b6d3670bc1a53dbe60d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="d0fb6-102">ICoreClrDebugTarget::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="d0fb6-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="d0fb6-103">원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0fb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0fb6-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0fb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0fb6-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="d0fb6-106">[out] `ppProcs`에 반환된 프로세스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="d0fb6-107">이 값은 0일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="d0fb6-108">[out] 배열을 [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) 원격 컴퓨터에서 실행 중인 프로세스를 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0fb6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d0fb6-109">Return Value</span></span>  
 <span data-ttu-id="d0fb6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0fb6-110">S_OK</span></span>  
 <span data-ttu-id="d0fb6-111">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="d0fb6-111">Success.</span></span>  
  
 <span data-ttu-id="d0fb6-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0fb6-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d0fb6-113">`ppProcs`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="d0fb6-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="d0fb6-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d0fb6-115">기타 실패</span><span class="sxs-lookup"><span data-stu-id="d0fb6-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0fb6-116">설명</span><span class="sxs-lookup"><span data-stu-id="d0fb6-116">Remarks</span></span>  
 <span data-ttu-id="d0fb6-117">이 메서드에 의해 할당 된 메모리를 확보 하기 위해 호출 된 [icoreclrdebugtarget:: Freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0fb6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0fb6-118">Requirements</span></span>  
 <span data-ttu-id="d0fb6-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fb6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0fb6-120">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d0fb6-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d0fb6-121">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d0fb6-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d0fb6-122">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d0fb6-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fb6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0fb6-123">See Also</span></span>  
 [<span data-ttu-id="d0fb6-124">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0fb6-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
