---
title: IcorDebugVariableHome::GetLiveRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0f9c586a9e95fc2e57c4956601f6dce2b988159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423067"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="3d4c5-102">IcorDebugVariableHome::GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="3d4c5-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="3d4c5-103">이 변수는 라이브 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d4c5-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d4c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d4c5-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d4c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d4c5-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="3d4c5-106">[out] 변수는 첫 번째 실시간 논리 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3d4c5-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="3d4c5-107">[out] 변수는 마지막 실시간 포인터 바로 뒤의 논리 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3d4c5-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d4c5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d4c5-108">Requirements</span></span>  
 <span data-ttu-id="3d4c5-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d4c5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d4c5-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d4c5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d4c5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d4c5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d4c5-112">**.NET framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d4c5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4c5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d4c5-113">See Also</span></span>  
 [<span data-ttu-id="3d4c5-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d4c5-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
