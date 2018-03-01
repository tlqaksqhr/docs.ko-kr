---
title: "ICorDebugILFrame::GetLocalVariable 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9694ee2e27d8789b661abc7393a480411c2b0191
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="bd389-102">ICorDebugILFrame::GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="bd389-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="bd389-103">이 Microsoft MSIL (intermediate language) 스택 프레임에서 지정 된 로컬 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd389-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd389-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd389-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd389-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd389-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="bd389-106">[in] MSIL이 스택 프레임에서 로컬 변수 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd389-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bd389-107">[out] 검색 된 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd389-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd389-108">설명</span><span class="sxs-lookup"><span data-stu-id="bd389-108">Remarks</span></span>  
 <span data-ttu-id="bd389-109">`GetLocalVariable` 시간 (JIT) 컴파일된 프레임 또는 MSIL 스택 프레임에 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd389-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd389-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd389-110">Requirements</span></span>  
 <span data-ttu-id="bd389-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd389-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd389-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd389-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd389-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd389-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd389-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd389-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
