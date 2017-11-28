---
title: "ICorDebugDataTarget2::EnumerateThreadIDs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c20b7dd1bcbc27edb9be11419b7919250301d488
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="48446-102">ICorDebugDataTarget2::EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="48446-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="48446-103">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="48446-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48446-104">구문</span><span class="sxs-lookup"><span data-stu-id="48446-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48446-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48446-105">Parameters</span></span>  
 <span data-ttu-id="48446-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="48446-106">cThreadIDs</span></span>  
 <span data-ttu-id="48446-107">[in] 스레드 ID를 반환할 수 있는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48446-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="48446-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="48446-108">pcThreadIds</span></span>  
 <span data-ttu-id="48446-109">[out] `ULONG32` 배열에 기록된 스레드 ID의 실제 수를 나타내는 `pThreadIds`에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48446-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="48446-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="48446-110">pThreadIDs</span></span>  
 <span data-ttu-id="48446-111">스레드 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="48446-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48446-112">설명</span><span class="sxs-lookup"><span data-stu-id="48446-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48446-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48446-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48446-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48446-114">Requirements</span></span>  
 <span data-ttu-id="48446-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md). **헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48446-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48446-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48446-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48446-117">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48446-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48446-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48446-118">See Also</span></span>  
 [<span data-ttu-id="48446-119">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48446-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="48446-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48446-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
