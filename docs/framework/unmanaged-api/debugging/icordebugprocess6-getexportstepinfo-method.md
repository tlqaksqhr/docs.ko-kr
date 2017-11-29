---
title: "ICorDebugProcess6::GetExportStepInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbb0e1cf904675005522002596476aec996124b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="30785-102">ICorDebugProcess6::GetExportStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="30785-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="30785-103">관리 코드를 단계별로 실행할 수 있도록 런타임에 내보낸 함수에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30785-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30785-104">구문</span><span class="sxs-lookup"><span data-stu-id="30785-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30785-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30785-105">Parameters</span></span>  
 <span data-ttu-id="30785-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="30785-106">pszExportName</span></span>  
 <span data-ttu-id="30785-107">[in] PE 내보내기 테이블에 기록된 런타임 내보내기 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30785-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="30785-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="30785-108">invokeKind</span></span>  
 <span data-ttu-id="30785-109">[out] 멤버에 대 한 포인터는 [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) 내보낸된 함수가 관리 코드를 호출할 방법을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="30785-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="30785-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="30785-110">invokePurpose</span></span>  
 <span data-ttu-id="30785-111">[out] 멤버에 대 한 포인터는 [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) 내보낸된 함수가 관리 코드를 호출 하는 이유를 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="30785-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30785-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="30785-112">Return Value</span></span>  
 <span data-ttu-id="30785-113">이 메서드는 다음 표에 나와 있는 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30785-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="30785-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="30785-114">Return value</span></span>|<span data-ttu-id="30785-115">설명</span><span class="sxs-lookup"><span data-stu-id="30785-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="30785-116">메서드 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="30785-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="30785-117">`pInvokeKind`또는 `pInvokePurpose` 은 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="30785-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="30785-118">기타 오류 `HRESULT` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="30785-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="30785-119">상황에 따라 적절하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="30785-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30785-120">설명</span><span class="sxs-lookup"><span data-stu-id="30785-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30785-121">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30785-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30785-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30785-122">Requirements</span></span>  
 <span data-ttu-id="30785-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30785-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30785-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30785-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30785-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30785-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30785-126">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30785-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30785-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30785-127">See Also</span></span>  
 [<span data-ttu-id="30785-128">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30785-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="30785-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30785-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
