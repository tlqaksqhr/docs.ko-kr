---
title: "ICorDebugVariableHome::GetOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f80a362d4b44d13c39218b9d7a0db11ef49f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="2f55b-102">ICorDebugVariableHome::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2f55b-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="2f55b-103">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f55b-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f55b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f55b-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f55b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f55b-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="2f55b-106">[out] 기본 레지스터 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="2f55b-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f55b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="2f55b-107">Return Value</span></span>  
 <span data-ttu-id="2f55b-108">메서드는 다음 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f55b-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2f55b-109">값</span><span class="sxs-lookup"><span data-stu-id="2f55b-109">Value</span></span>|<span data-ttu-id="2f55b-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f55b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2f55b-111">변수가 메모리 레지스터 상대 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2f55b-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2f55b-112">변수는 레지스터 상대 메모리 위치에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="2f55b-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f55b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f55b-113">Requirements</span></span>  
 <span data-ttu-id="2f55b-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f55b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f55b-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f55b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f55b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f55b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f55b-117">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f55b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f55b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f55b-118">See Also</span></span>  
 [<span data-ttu-id="2f55b-119">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f55b-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
