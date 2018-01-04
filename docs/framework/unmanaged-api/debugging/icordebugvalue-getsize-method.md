---
title: "ICorDebugValue::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5cf99b35d45c1dda8f187e0206e068c128f347d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="920f8-102">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="920f8-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="920f8-103">이 "ICorDebugValue" 개체를 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="920f8-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="920f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="920f8-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="920f8-106">[out] 이 값 개체를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="920f8-107">설명</span><span class="sxs-lookup"><span data-stu-id="920f8-107">Remarks</span></span>  
 <span data-ttu-id="920f8-108">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기 보다는 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="920f8-109">`ICorDebugValue::GetSize` 메서드 반환 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="920f8-110">사용 하 여 [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 대신 개체 수 있는 4GB 보다 큰 합니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="920f8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="920f8-111">Requirements</span></span>  
 <span data-ttu-id="920f8-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="920f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="920f8-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="920f8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="920f8-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="920f8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="920f8-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="920f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920f8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="920f8-116">See Also</span></span>  
    
 [<span data-ttu-id="920f8-117">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="920f8-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
