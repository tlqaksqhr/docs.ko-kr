---
title: "PutMethod 함수 (관리 되지 않는 API 참조)"
description: "PutMethod 함수는 메서드를 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a><span data-ttu-id="11c97-103">PutMethod 함수</span><span class="sxs-lookup"><span data-stu-id="11c97-103">PutMethod function</span></span>
<span data-ttu-id="11c97-104">메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="11c97-105">구문</span><span class="sxs-lookup"><span data-stu-id="11c97-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="11c97-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11c97-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="11c97-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="11c97-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="11c97-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="11c97-109">[in] 만드는 방법의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="11c97-110">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-110">[in] Reserved.</span></span> <span data-ttu-id="11c97-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="11c97-112">[in] 복사본에 대 한 포인터는 [__Parameters 시스템 클래스](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 를 포함 하는 `in` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-112">[in] A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="11c97-113">이 매개 변수는 설정 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="11c97-114">[in]  복사본에 대 한 포인터는 [__Parameters 시스템 클래스](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 를 포함 하는 `out` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-114">[in]  A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="11c97-115">이 매개 변수는 설정 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="11c97-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="11c97-116">Return value</span></span>

<span data-ttu-id="11c97-117">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="11c97-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="11c97-118">상수</span><span class="sxs-lookup"><span data-stu-id="11c97-118">Constant</span></span>  |<span data-ttu-id="11c97-119">값</span><span class="sxs-lookup"><span data-stu-id="11c97-119">Value</span></span>  |<span data-ttu-id="11c97-120">설명</span><span class="sxs-lookup"><span data-stu-id="11c97-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="11c97-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="11c97-121">0x80041008</span></span> | <span data-ttu-id="11c97-122">하나 이상의 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="11c97-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="11c97-123">0x80041043</span></span> | <span data-ttu-id="11c97-124">`[in, out]` 모두에 지정 된 메서드 매개 변수는 *pInSignature* 및 *pOutSignature* 개체에는 다른 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="11c97-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="11c97-125">0x80041036</span></span> | <span data-ttu-id="11c97-126">메서드 매개 변수의 사양이 없습니다는 **ID** 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="11c97-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="11c97-127">0x80041038</span></span> | <span data-ttu-id="11c97-128">메서드 매개 변수에 할당 된 ID 시리즈 연속 되었거나 0으로 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="11c97-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="11c97-129">0x80041039</span></span> | <span data-ttu-id="11c97-130">메서드에 대 한 반환 값에는 **ID** 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="11c97-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="11c97-131">0x80041034</span></span> | <span data-ttu-id="11c97-132">부모 클래스에서 기존 메서드 이름을 다시 사용 하려고 했습니다 및 서명이 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="11c97-133">0</span><span class="sxs-lookup"><span data-stu-id="11c97-133">0</span></span> | <span data-ttu-id="11c97-134">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="11c97-135">설명</span><span class="sxs-lookup"><span data-stu-id="11c97-135">Remarks</span></span>

<span data-ttu-id="11c97-136">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="11c97-136">This function wraps a call to the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="11c97-137">이 메서드를 호출 하는 경우만 지원 됩니다 `ptr` CIM 클래스 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="11c97-138">조작 메서드를 사용할 수 없기 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) CIM 인스턴스를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-138">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) pointers that point to CIM instances.</span></span>

<span data-ttu-id="11c97-139">사용자가 시작 또는 밑줄로 끝나야 하는 이름을 가진 메서드를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="11c97-140">이 시스템 클래스 및 속성에 대해 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="11c97-141">메서드에 대 한는 `in` 및 `out` 매개 변수에서 속성으로 설명 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objects.</span></span>

<span data-ttu-id="11c97-142">`[in/out]` 가리키는 두 개체 모두에 동일한 속성을 추가 하 여 매개 변수를 정의할 수 있습니다는 `pInSignature` 및 `pOutSignature` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="11c97-143">이 경우 속성 공유 동일한 **ID** 한정자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="11c97-144">각 속성에는 [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 개체 이외의 클래스 `ReturnValue` 있어야는 **ID** 한정자, 매개 변수가 나타나는 순서를 식별 하는 숫자 값을 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-144">Each property in a [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="11c97-145">동일한 두 개의 매개 변수가 없는 가질 수 있습니다 **ID** 값 및 아니요 **ID** 값을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="11c97-146">두 조건 중 하나가 발생 하는 경우는 `PutMethod` 함수에서 반환 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="11c97-147">예</span><span class="sxs-lookup"><span data-stu-id="11c97-147">Example</span></span>

<span data-ttu-id="11c97-148">예를 들어 참조는 [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="11c97-148">For an example, see the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="11c97-149">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11c97-149">Requirements</span></span>  
 <span data-ttu-id="11c97-150">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11c97-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c97-151">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="11c97-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="11c97-152">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11c97-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c97-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11c97-153">See also</span></span>  
[<span data-ttu-id="11c97-154">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="11c97-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
