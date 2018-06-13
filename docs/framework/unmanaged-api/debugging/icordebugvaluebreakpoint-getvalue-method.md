---
title: ICorDebugValueBreakpoint::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8ff07c483ef1bcbf9d5141b7180cea08454ebef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417101"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="3b987-102">ICorDebugValueBreakpoint::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="3b987-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="3b987-103">중단점이 설정 된 개체의 값을 나타내는 "ICorDebugValue" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b987-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b987-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b987-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b987-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b987-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="3b987-106">[out] 주소에 대 한 포인터는 `ICorDebugValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3b987-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b987-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b987-107">Requirements</span></span>  
 <span data-ttu-id="3b987-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b987-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b987-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b987-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b987-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b987-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b987-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b987-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b987-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b987-112">See Also</span></span>  
 
