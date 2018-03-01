---
title: "Put 함수 (관리 되지 않는 API 참조)"
description: "Put 함수는 명명된 된 속성에 새 값을 할당합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09d3edc74b34688d5cc36e688f634850cfb60910
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="put-function"></a><span data-ttu-id="b73ea-103">Put 함수</span><span class="sxs-lookup"><span data-stu-id="b73ea-103">Put function</span></span>
<span data-ttu-id="b73ea-104">명명된 된 속성을 새 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b73ea-105">구문</span><span class="sxs-lookup"><span data-stu-id="b73ea-105">Syntax</span></span>  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a><span data-ttu-id="b73ea-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b73ea-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b73ea-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b73ea-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b73ea-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="b73ea-109">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-109">[in] The name of the property.</span></span> <span data-ttu-id="b73ea-110">이 매개 변수 여야 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-110">This parameter cannot be `null`.</span></span>

`lFlags`  
<span data-ttu-id="b73ea-111">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-111">[in] Reserved.</span></span> <span data-ttu-id="b73ea-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-112">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="b73ea-113">[in] 에 대 한 포인터를 올바른 `VARIANT` 하는 새 속성 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="b73ea-114">경우 `pVal` 은 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`는 속성이로 설정 된 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span> 

`vtType`  
<span data-ttu-id="b73ea-115">[in] 유형의 `VARIANT` 가리키는 `pVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="b73ea-116">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-116">See the [Remarks](#remarks) section for more information.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="b73ea-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="b73ea-117">Return value</span></span>

<span data-ttu-id="b73ea-118">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="b73ea-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b73ea-119">상수</span><span class="sxs-lookup"><span data-stu-id="b73ea-119">Constant</span></span>  |<span data-ttu-id="b73ea-120">값</span><span class="sxs-lookup"><span data-stu-id="b73ea-120">Value</span></span>  |<span data-ttu-id="b73ea-121">설명</span><span class="sxs-lookup"><span data-stu-id="b73ea-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b73ea-122">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="b73ea-122">0x80041001</span></span> | <span data-ttu-id="b73ea-123">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b73ea-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b73ea-124">0x80041008</span></span> | <span data-ttu-id="b73ea-125">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="b73ea-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="b73ea-126">0x8004102a</span></span> | <span data-ttu-id="b73ea-127">속성 유형이 인식 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-127">The property type is not recognized.</span></span> <span data-ttu-id="b73ea-128">클래스가 이미 존재 하는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b73ea-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b73ea-129">0x80041006</span></span> | <span data-ttu-id="b73ea-130">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b73ea-131">0x80041005가</span><span class="sxs-lookup"><span data-stu-id="b73ea-131">0x80041005</span></span> | <span data-ttu-id="b73ea-132">에 대 한 인스턴스: 나타냅니다 `pVal` 가리키는 `VARIANT` 속성에 대 한 잘못 된 유형의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="b73ea-133">클래스 정의 대 한: 속성이 부모 클래스에 이미 및 새 COM 형식을 이전 COM 종류와에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b73ea-134">0</span><span class="sxs-lookup"><span data-stu-id="b73ea-134">0</span></span> | <span data-ttu-id="b73ea-135">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-135">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b73ea-136">설명</span><span class="sxs-lookup"><span data-stu-id="b73ea-136">Remarks</span></span>

<span data-ttu-id="b73ea-137">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b73ea-137">This function wraps a call to the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b73ea-138">이 함수는 새 항목으로는 현재 속성 값을 항상 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="b73ea-139">경우는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 클래스 정의 가리키는 `Put` 만들거나 속성 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-139">If the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="b73ea-140">때 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 `Put` 속성 값만 사용 합니다;이 업데이트 `Put` 속성 값을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-140">When [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="b73ea-141">`__CLASS` 시스템 속성은 쓰기 가능한 클래스를 만드는 동안 때만 것 하지 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="b73ea-142">다른 모든 시스템 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-142">All other system properties are read-only.</span></span>

<span data-ttu-id="b73ea-143">사용자는 밑줄 ("_")으로 시작 하거나 끝나서는 이름으로 속성을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="b73ea-144">이 시스템 클래스 및 속성에 대해 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="b73ea-145">속성으로 설정 하는 경우는 `Put` 속성 형식은 부모 클래스 형식과 일치 하지 않는 하지 않는 한 속성의 기본값은 변경, 부모 클래스에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="b73ea-146">속성이 존재 하지 않는 경우 형식이 일치 하지 않습니다 속성이 ceated입니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-146">If the property does not exist and it is not a type mismatch, the property is ceated.</span></span>

<span data-ttu-id="b73ea-147">사용 하 여는 `vtType` CIM 클래스 정의에서 새 속성을 만들 때에 매개 변수 및 `pVal` 은 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="b73ea-148">이 경우에 `vType` 매개 변수 속성의 CIM 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="b73ea-149">다른 모든 경우에 `vtType` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="b73ea-150">`vtType`0 이어야 기본 개체 인스턴스 라면 (경우에 `Val` 은 `null`) 속성의 형식이 고정 되어 있고 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>   

## <a name="example"></a><span data-ttu-id="b73ea-151">예</span><span class="sxs-lookup"><span data-stu-id="b73ea-151">Example</span></span>

<span data-ttu-id="b73ea-152">예를 들어 참조는 [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b73ea-152">For an example, see the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b73ea-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b73ea-153">Requirements</span></span>  
 <span data-ttu-id="b73ea-154">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ea-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b73ea-155">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b73ea-155">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b73ea-156">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b73ea-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73ea-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b73ea-157">See also</span></span>  
[<span data-ttu-id="b73ea-158">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b73ea-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
