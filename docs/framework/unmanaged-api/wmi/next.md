---
title: "Next 함수 (관리 되지 않는 API 참조)"
description: "다음 함수 retireves 열거형에서 다음 속성입니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Next
helpviewer_keywords: Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a><span data-ttu-id="1f69d-103">Next 함수</span><span class="sxs-lookup"><span data-stu-id="1f69d-103">Next function</span></span>
<span data-ttu-id="1f69d-104">에 대 한 호출으로 시작 하는 열거형에서 다음 속성을 검색 [BeginEnumeration](beginenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1f69d-105">구문</span><span class="sxs-lookup"><span data-stu-id="1f69d-105">Syntax</span></span>  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a><span data-ttu-id="1f69d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f69d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1f69d-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1f69d-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1f69d-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="1f69d-109">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-109">[in] Reserved.</span></span> <span data-ttu-id="1f69d-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="1f69d-111">[out] 새 `BSTR` 속성 이름이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="1f69d-112">이 매개 변수를 설정할 수 있습니다 `null` 이름이 필요 하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="1f69d-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="1f69d-113">[out] A `VARIANT` 속성의 값으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="1f69d-114">이 매개 변수를 설정할 수 있습니다 `null` 값이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="1f69d-115">함수는 오류 코드를 반환 하는 경우는 `VARIANT` 에 전달 된 `pVal` 왼쪽 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="1f69d-116">[out] 에 대 한 포인터는 `CIMTYPE` 변수 (한 `LONG` 속성의 형식을 추가 하는에).</span><span class="sxs-lookup"><span data-stu-id="1f69d-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="1f69d-117">이 속성의 값 수는 `VT_NULL_VARIANT`, 실제 형식의 속성을 확인 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="1f69d-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="1f69d-118">또한이 매개 변수 수 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="1f69d-119">[out] `null`, 또는 속성의 출처 정보를 수신 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="1f69d-120">가능한 값은 [설명] 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1f69d-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f69d-121">Return value</span></span>

<span data-ttu-id="1f69d-122">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="1f69d-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1f69d-123">상수</span><span class="sxs-lookup"><span data-stu-id="1f69d-123">Constant</span></span>  |<span data-ttu-id="1f69d-124">값</span><span class="sxs-lookup"><span data-stu-id="1f69d-124">Value</span></span>  |<span data-ttu-id="1f69d-125">설명</span><span class="sxs-lookup"><span data-stu-id="1f69d-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1f69d-126">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="1f69d-126">0x80041001</span></span> | <span data-ttu-id="1f69d-127">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1f69d-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1f69d-128">0x80041008</span></span> | <span data-ttu-id="1f69d-129">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="1f69d-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1f69d-130">0x8004101d</span></span> | <span data-ttu-id="1f69d-131">에 대 한 호출이 했습니다는 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1f69d-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1f69d-132">0x80041006</span></span> | <span data-ttu-id="1f69d-133">새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="1f69d-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="1f69d-134">0x80041015</span></span> | <span data-ttu-id="1f69d-135">현재 프로세스와 Windows 관리 하지 못했습니다 원격 프로시저 간에 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1f69d-136">0</span><span class="sxs-lookup"><span data-stu-id="1f69d-136">0</span></span> | <span data-ttu-id="1f69d-137">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="1f69d-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="1f69d-138">0x40005</span></span> | <span data-ttu-id="1f69d-139">열거형에 더 많은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="1f69d-140">설명</span><span class="sxs-lookup"><span data-stu-id="1f69d-140">Remarks</span></span>

<span data-ttu-id="1f69d-141">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1f69d-141">This function wraps a call to the [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1f69d-142">또한이 메서드는 시스템 속성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-142">This method also returns system properties.</span></span>

<span data-ttu-id="1f69d-143">속성의 내부 형식이 개체 경로, 날짜 또는 시간 또는 다른 특수 형식 인 경우 다음 반환 된 형식에 충분 한 정보</span><span class="sxs-lookup"><span data-stu-id="1f69d-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="1f69d-144">호출자에 게 검사 해야 하는 `CIMTYPE` 속성이 개체 참조, 날짜 또는 시간 또는 다른 특별 한 형식 인지 확인 하려면 지정 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="1f69d-145">경우 `plFlavor` 않습니다 `null`, `LONG` 값 속성의 원점에 대 한 정보를 다음과 같이 수신:</span><span class="sxs-lookup"><span data-stu-id="1f69d-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="1f69d-146">상수</span><span class="sxs-lookup"><span data-stu-id="1f69d-146">Constant</span></span>  |<span data-ttu-id="1f69d-147">값</span><span class="sxs-lookup"><span data-stu-id="1f69d-147">Value</span></span>  |<span data-ttu-id="1f69d-148">설명</span><span class="sxs-lookup"><span data-stu-id="1f69d-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="1f69d-149">0x40</span><span class="sxs-lookup"><span data-stu-id="1f69d-149">0x40</span></span> | <span data-ttu-id="1f69d-150">속성에는 표준 시스템 속성이입니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="1f69d-151">0x20</span><span class="sxs-lookup"><span data-stu-id="1f69d-151">0x20</span></span> | <span data-ttu-id="1f69d-152">클래스에 대 한:의 속성이 부모 클래스 로부터 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="1f69d-153">인스턴스에 대 한: 속성을 부모 클래스에서 상속 하는 동안 수정 되지 않은 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="1f69d-154">0</span><span class="sxs-lookup"><span data-stu-id="1f69d-154">0</span></span> | <span data-ttu-id="1f69d-155">클래스에 대 한: 속성이 파생된 클래스에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="1f69d-156">인스턴스에 대 한: 인스턴스에서; 속성이 수정 되 즉, 값이 제공 된 또는 한정자가 추가 되거나 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="1f69d-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f69d-157">Requirements</span></span>  
 <span data-ttu-id="1f69d-158">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f69d-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f69d-159">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1f69d-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1f69d-160">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f69d-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f69d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f69d-161">See also</span></span>  
[<span data-ttu-id="1f69d-162">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1f69d-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
