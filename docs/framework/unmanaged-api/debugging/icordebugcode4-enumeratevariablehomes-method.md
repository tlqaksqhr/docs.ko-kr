---
title: ICorDebugCode4::EnumerateVariableHomes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1c8157d5a5e4a1bd52f187de7c1d3bfcc4e66d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410922"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="ce728-102">ICorDebugCode4::EnumerateVariableHomes 메서드</span><span class="sxs-lookup"><span data-stu-id="ce728-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="ce728-103">함수에서 지역 변수 및 인수에는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce728-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce728-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce728-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce728-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce728-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ce728-106">주소에 대 한 포인터는 [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 인터페이스 개체 지역 변수 및 인수는 함수에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce728-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce728-107">설명</span><span class="sxs-lookup"><span data-stu-id="ce728-107">Remarks</span></span>  
 <span data-ttu-id="ce728-108">[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) 인터페이스 개체는 열거할 수 있도록 "ICorDebugEnum" 인터페이스에서 파생 된 표준 열거자 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce728-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="ce728-109">컬렉션에 여러 개 포함 될 수 있습니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 함수에서 여러 시점에서 다른 호밍하 있는 경우 동일한 슬롯 또는 인수 인덱스에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ce728-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce728-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce728-110">Requirements</span></span>  
 <span data-ttu-id="ce728-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce728-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce728-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce728-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce728-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce728-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce728-114">**.NET framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce728-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce728-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce728-115">See Also</span></span>  
 [<span data-ttu-id="ce728-116">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce728-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 [<span data-ttu-id="ce728-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce728-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
