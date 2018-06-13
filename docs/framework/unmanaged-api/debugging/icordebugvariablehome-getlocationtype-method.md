---
title: ICorDebugVariableHome::GetLocationType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c04fa944f2a3da9b6548ada36443d5dda4725f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421131"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="85c6c-102">ICorDebugVariableHome::GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="85c6c-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="85c6c-103">변수의 네이티브 위치의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c6c-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c6c-104">구문</span><span class="sxs-lookup"><span data-stu-id="85c6c-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85c6c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85c6c-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="85c6c-106">[out] 변수의 네이티브 위치 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="85c6c-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="85c6c-107">참조는 [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) 자세한 정보에 대 한 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="85c6c-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c6c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85c6c-108">Requirements</span></span>  
 <span data-ttu-id="85c6c-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85c6c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c6c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85c6c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85c6c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85c6c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85c6c-112">**.NET framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c6c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c6c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85c6c-113">See Also</span></span>  
 [<span data-ttu-id="85c6c-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85c6c-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="85c6c-115">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="85c6c-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
