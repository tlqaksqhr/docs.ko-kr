---
title: "ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ac4cc32be6914ea858d32b8699a695588f0a1e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="a8b66-102">ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="a8b66-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="a8b66-103">가비지 수집을 처리 하는 지정된 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b66-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8b66-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8b66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8b66-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="a8b66-106">[in] 가비지 컬렉션 핸들을 가진 관리 되는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="a8b66-107">이 값은 한 <xref:System.IntPtr> 개체 및에서 검색할 수는 <xref:System.Runtime.InteropServices.GCHandle> 관리 되는 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="a8b66-108">[out] 지정된 된 관리 되는 개체에 대 한 참조를 나타내는 ICorDebugReferenceValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8b66-109">설명</span><span class="sxs-lookup"><span data-stu-id="a8b66-109">Remarks</span></span>  
 <span data-ttu-id="a8b66-110">가비지 컬렉션 참조 값으로 반환 된 참조 값을 혼동 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a8b66-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="a8b66-111">반환 된 참조는 일반적인 참조 처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="a8b66-112">코드 실행이 중단점 후 계속 하는 경우 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="a8b66-113">대상 개체의 수명은 참조 값의 수명에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8b66-114">`GetReferenceValueFromGCHandle` 메서드 핸들을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="a8b66-115">따라서는 `GetReferenceValueFromGCHandle` 메서드는 디버거와 잘못 된 핸들이 전달 될 경우 디버깅 중인 코드에 잠재적으로 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b66-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8b66-116">Requirements</span></span>  
 <span data-ttu-id="a8b66-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8b66-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b66-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8b66-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8b66-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8b66-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8b66-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b66-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
