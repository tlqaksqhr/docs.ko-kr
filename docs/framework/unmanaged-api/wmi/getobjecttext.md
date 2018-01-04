---
title: "GetObjectText 함수 (관리 되지 않는 API 참조)"
description: "GetObjectText 함수 MOF 구문으로 개체의 텍스트 렌더링을 반환합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a><span data-ttu-id="fa6c9-103">GetObjectText 함수</span><span class="sxs-lookup"><span data-stu-id="fa6c9-103">GetObjectText function</span></span>
<span data-ttu-id="fa6c9-104">관리 되는 MOF (Object Format) 구문에서 개체의 텍스트 렌더링을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="fa6c9-105">구문</span><span class="sxs-lookup"><span data-stu-id="fa6c9-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="fa6c9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa6c9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fa6c9-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fa6c9-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="fa6c9-109">[in] 일반적으로 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-109">[in] Normally 0.</span></span> <span data-ttu-id="fa6c9-110">경우 `WBEM_FLAG_NO_FLAVORS` (또는 0x1)을 지정 한정자는 전파 또는 버전 정보 없이 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="fa6c9-111">[out] 에 대 한 포인터는 `null` 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="fa6c9-112">반환 시 새로 할당 된 `BSTR` 개체의 MOF 구문 렌더링을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="fa6c9-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="fa6c9-113">Return value</span></span>

<span data-ttu-id="fa6c9-114">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="fa6c9-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fa6c9-115">상수</span><span class="sxs-lookup"><span data-stu-id="fa6c9-115">Constant</span></span>  |<span data-ttu-id="fa6c9-116">값</span><span class="sxs-lookup"><span data-stu-id="fa6c9-116">Value</span></span>  |<span data-ttu-id="fa6c9-117">설명</span><span class="sxs-lookup"><span data-stu-id="fa6c9-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fa6c9-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="fa6c9-118">0x80041001</span></span> | <span data-ttu-id="fa6c9-119">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fa6c9-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fa6c9-120">0x80041008</span></span> | <span data-ttu-id="fa6c9-121">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fa6c9-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fa6c9-122">0x80041006</span></span> | <span data-ttu-id="fa6c9-123">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fa6c9-124">0</span><span class="sxs-lookup"><span data-stu-id="fa6c9-124">0</span></span> | <span data-ttu-id="fa6c9-125">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fa6c9-126">설명</span><span class="sxs-lookup"><span data-stu-id="fa6c9-126">Remarks</span></span>

<span data-ttu-id="fa6c9-127">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="fa6c9-128">개체에 대 한 모든 정보는 있지만 원본 개체를 다시 만들 수 있게 되기를 MOF 컴파일러에 대 한 충분 한 정보만 반환 하는 MOF 텍스트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="fa6c9-129">예를 들어, 없습니다 전파 한정자 또는 부모 클래스 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="fa6c9-130">다음 알고리즘은 메서드의 매개 변수 텍스트를 다시 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="fa6c9-131">매개 변수는 해당 식별자 값 순서 대로 resequenced 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="fa6c9-132">으로 지정 된 매개 변수 `[in]` 및 `[out]` 단일 매개 변수를 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="fa6c9-133">`pstrObjectText`에 대 한 포인터 여야 합니다는 `null` 함수를 호출할 때는 하지를 가리켜야 포인터가 할당을 취소할 수는 때문에 메서드 호출 전에 올바르지 않은 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa6c9-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa6c9-134">Requirements</span></span>  
<span data-ttu-id="fa6c9-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6c9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6c9-136">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fa6c9-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fa6c9-137">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6c9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6c9-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa6c9-138">See also</span></span>  
[<span data-ttu-id="fa6c9-139">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="fa6c9-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
