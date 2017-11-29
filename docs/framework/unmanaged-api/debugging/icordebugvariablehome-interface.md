---
title: "ICorDebugVariableHome 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea8f4033a6b0878288c49d6f6d964eb40675162d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="dd609-102">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd609-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="dd609-103">지역 변수 또는 함수 '의 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd609-104">메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-104">Methods</span></span>  
  
|<span data-ttu-id="dd609-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-105">Method</span></span>|<span data-ttu-id="dd609-106">설명</span><span class="sxs-lookup"><span data-stu-id="dd609-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd609-107">GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="dd609-108">함수 인수 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="dd609-109">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="dd609-110">이 포함 하는 "ICorDebugCode" 인스턴스로 가져옵니다 `ICorDebugVariableHome` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="dd609-111">GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="dd609-112">이 변수는 라이브 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="dd609-113">GetLocationType 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="dd609-114">변수의 네이티브 위치의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="dd609-115">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="dd609-116">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="dd609-117">GetRegister 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="dd609-118">위치 유형 변수를 포함 하는 레지스터 가져옵니다 `VLT_REGISTER`와의 위치 유형 변수에 대 한 기본 레지스터 `VLT_REGISTER_RELATIVE`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="dd609-119">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="dd609-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="dd609-120">지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd609-121">예제</span><span class="sxs-lookup"><span data-stu-id="dd609-121">Example</span></span>  
 <span data-ttu-id="dd609-122">다음 코드 조각에서는 [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) 라는 개체 `pCode4`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="dd609-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd609-123">Requirements</span></span>  
 <span data-ttu-id="dd609-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd609-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd609-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd609-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd609-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd609-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd609-127">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd609-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd609-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd609-128">See Also</span></span>  
 [<span data-ttu-id="dd609-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd609-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dd609-130">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd609-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
