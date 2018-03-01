---
title: "ICorDebugFrame::GetStackRange 메서드"
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
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c4c9c0a531d93ca2c7c72f50bcd2f7ee98887e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="6ae88-102">ICorDebugFrame::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="6ae88-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="6ae88-103">이 스택 프레임의 절대 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ae88-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ae88-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ae88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ae88-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="6ae88-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 표시 되는 스택 프레임의 시작 주소를 지정 하는 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="6ae88-107">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 표시 되는 스택 프레임의 끝 주소를 지정 하는 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ae88-108">설명</span><span class="sxs-lookup"><span data-stu-id="6ae88-108">Remarks</span></span>  
 <span data-ttu-id="6ae88-109">스택의 주소 범위는 정보를 결합 인터리브 스택 추적 여러 디버깅 엔진에서 수집 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="6ae88-110">숫자 범위는 스택 프레임의 내용 관련 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="6ae88-111">스택 프레임 위치를 비교 하기 위해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ae88-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ae88-112">Requirements</span></span>  
 <span data-ttu-id="6ae88-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae88-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae88-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ae88-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ae88-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ae88-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ae88-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae88-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
