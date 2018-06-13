---
title: ICorDebugMergedAssemblyRecord::GetIndex 메서드
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0bcb5cdb4e93ae8ce6981bd86f125ecccb7d732
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414838"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="75e0d-102">ICorDebugMergedAssemblyRecord::GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="75e0d-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="75e0d-103">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e0d-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="75e0d-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75e0d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75e0d-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="75e0d-106">[out] 접두사 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="75e0d-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75e0d-107">설명</span><span class="sxs-lookup"><span data-stu-id="75e0d-107">Remarks</span></span>  
 <span data-ttu-id="75e0d-108">접두사 인덱스는 병합된 메타데이터 형식 이름에서 이름 충돌을 방지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e0d-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75e0d-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e0d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e0d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75e0d-110">Requirements</span></span>  
 <span data-ttu-id="75e0d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75e0d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e0d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75e0d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75e0d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e0d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e0d-114">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e0d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e0d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75e0d-115">See Also</span></span>  
 [<span data-ttu-id="75e0d-116">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75e0d-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="75e0d-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75e0d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
