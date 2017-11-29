---
title: "ICorDebugProcess5::GetTypeForTypeID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeForTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08c4b72b5b37d9e3a2a2e19bad9e79449906b495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="7a718-102">ICorDebugProcess5::GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="7a718-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="7a718-103">유형 식별자 ICorDebugType 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a718-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a718-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a718-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a718-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7a718-106">[in] 유형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="7a718-107">[out] ICorDebugType 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a718-108">설명</span><span class="sxs-lookup"><span data-stu-id="7a718-108">Remarks</span></span>  
 <span data-ttu-id="7a718-109">경우에 따라 형식 식별자를 반환 하는 메서드는 null을 반환 `COR_TYPEID` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="7a718-110">이 값으로 전달 될는 `id` 인수는 `GetTypeForTypeID` 메서드를 반환 `E_FAIL`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a718-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a718-111">Requirements</span></span>  
 <span data-ttu-id="7a718-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a718-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a718-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a718-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a718-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a718-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a718-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a718-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a718-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a718-116">See Also</span></span>  
 [<span data-ttu-id="7a718-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a718-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="7a718-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a718-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
