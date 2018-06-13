---
title: ICorDebugDataTarget2::EnumerateThreadIDs 메서드
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d915c7d5521e630602f4dac6c905920fd2fab9d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411449"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="c9488-102">ICorDebugDataTarget2::EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="c9488-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="c9488-103">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9488-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9488-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9488-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9488-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9488-105">Parameters</span></span>  
 <span data-ttu-id="c9488-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="c9488-106">cThreadIDs</span></span>  
 <span data-ttu-id="c9488-107">[in] 스레드 ID를 반환할 수 있는 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c9488-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="c9488-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="c9488-108">pcThreadIds</span></span>  
 <span data-ttu-id="c9488-109">[out] `ULONG32` 배열에 기록된 스레드 ID의 실제 수를 나타내는 `pThreadIds`에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c9488-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="c9488-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="c9488-110">pThreadIDs</span></span>  
 <span data-ttu-id="c9488-111">스레드 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c9488-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9488-112">설명</span><span class="sxs-lookup"><span data-stu-id="c9488-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9488-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9488-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9488-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9488-114">Requirements</span></span>  
 <span data-ttu-id="c9488-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md). **헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9488-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9488-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9488-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9488-117">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9488-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9488-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9488-118">See Also</span></span>  
 [<span data-ttu-id="c9488-119">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9488-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="c9488-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9488-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
