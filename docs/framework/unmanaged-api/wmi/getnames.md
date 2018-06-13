---
title: GetNames 함수 (관리 되지 않는 API 참조)
description: GetNames 함수 개체의 속성의 이름을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 108946428cdfadcfb9c653b7e444bf278dfa2782
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461983"
---
# <a name="getnames-function"></a><span data-ttu-id="7c70d-103">GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="7c70d-103">GetNames function</span></span>
<span data-ttu-id="7c70d-104">하위 집합 또는 모든 개체의 속성 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7c70d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c70d-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="7c70d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c70d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7c70d-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7c70d-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7c70d-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="7c70d-109">[in] 에 대 한 포인터를 올바른 `LPCWSTR` 작동 하는 한정자 이름 필터의 일부분으로 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="7c70d-110">자세한 내용은 참조는 [주의](#remarks) 섹션.</span><span class="sxs-lookup"><span data-stu-id="7c70d-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="7c70d-111">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="7c70d-112">[in] 비트 필드의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="7c70d-113">자세한 내용은 참조는 [주의](#remarks) 섹션.</span><span class="sxs-lookup"><span data-stu-id="7c70d-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="7c70d-114">[in] 에 대 한 포인터를 올바른 `VARIANT` 구조 필터 값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="7c70d-115">이 매개 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="7c70d-116">[out] A `SAFEARRAY` 속성 이름이 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="7c70d-117">이 매개 변수 입력 시에 대 한 포인터를 일 항상 해야 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="7c70d-118">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="7c70d-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c70d-119">Return value</span></span>

<span data-ttu-id="7c70d-120">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="7c70d-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7c70d-121">상수</span><span class="sxs-lookup"><span data-stu-id="7c70d-121">Constant</span></span>  |<span data-ttu-id="7c70d-122">값</span><span class="sxs-lookup"><span data-stu-id="7c70d-122">Value</span></span>  |<span data-ttu-id="7c70d-123">설명</span><span class="sxs-lookup"><span data-stu-id="7c70d-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7c70d-124">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="7c70d-124">0x80041001</span></span> | <span data-ttu-id="7c70d-125">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7c70d-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7c70d-126">0x80041008</span></span> | <span data-ttu-id="7c70d-127">하나 이상의 매개 변수가 유효 하지 않음 또는 플래그 및 매개 변수는 잘못 된 조합이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7c70d-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7c70d-128">0x80041006</span></span> | <span data-ttu-id="7c70d-129">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7c70d-130">0</span><span class="sxs-lookup"><span data-stu-id="7c70d-130">0</span></span> | <span data-ttu-id="7c70d-131">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7c70d-132">설명</span><span class="sxs-lookup"><span data-stu-id="7c70d-132">Remarks</span></span>

<span data-ttu-id="7c70d-133">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="7c70d-133">This function wraps a call to the [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="7c70d-134">반환 된 명명 된 매개 변수 및 플래그의 조합에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="7c70d-135">예를 들어 함수에는 모든 속성 이름이 나 키 속성의 이름에만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="7c70d-136">기본 필터에 지정 된는 `lFlags` 매개 변수 및 다른 매개 변수와 그에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="7c70d-137">플래그 값에 `lFlags` 는 비트 필드</span><span class="sxs-lookup"><span data-stu-id="7c70d-137">The flag values in `lFlags` are bit fields</span></span>


<span data-ttu-id="7c70d-138">로 전달 될 수 있는 플래그는 `lEnumFlags` 인수는에 정의 되어 있는 비트 필드는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7c70d-139">다른 그룹의 모든 플래그와 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7c70d-140">그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="7c70d-141">그룹 1 플래그</span><span class="sxs-lookup"><span data-stu-id="7c70d-141">Group 1 flags</span></span> |<span data-ttu-id="7c70d-142">값</span><span class="sxs-lookup"><span data-stu-id="7c70d-142">Value</span></span>  |<span data-ttu-id="7c70d-143">설명</span><span class="sxs-lookup"><span data-stu-id="7c70d-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="7c70d-144">0</span><span class="sxs-lookup"><span data-stu-id="7c70d-144">0</span></span> | <span data-ttu-id="7c70d-145">모든 속성 이름이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-145">Return all property names.</span></span> <span data-ttu-id="7c70d-146">`strQualifierName` 및 `pQualifierVal` 이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="7c70d-147">1</span><span class="sxs-lookup"><span data-stu-id="7c70d-147">1</span></span> | <span data-ttu-id="7c70d-148">지정 된 이름의 한정자가 있는 속성에만 반환는 `strQualifierName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7c70d-149">지정 해야이 플래그를 사용할 경우 `strQualifierName`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="7c70d-150">2</span><span class="sxs-lookup"><span data-stu-id="7c70d-150">2</span></span> |  <span data-ttu-id="7c70d-151">지정 된 이름의 한정자가 없는 속성에만 반환는 `strQualifierName` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7c70d-152">지정 해야이 플래그를 사용할 경우 `strQualifierName`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="7c70d-153">3</span><span class="sxs-lookup"><span data-stu-id="7c70d-153">3</span></span> | <span data-ttu-id="7c70d-154">속성에서 지정 된 이름의 한정자가을 반환는 `wszQualifierName` 매개 변수 및 값에 지정 된 동일한도 `pQualifierVal` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="7c70d-155">둘 다 지정 해야이 플래그를 사용 하는 경우는 `wszQualifierName` 및 `pQualifierValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="7c70d-156">그룹 2 플래그</span><span class="sxs-lookup"><span data-stu-id="7c70d-156">Group 2 flags</span></span> |<span data-ttu-id="7c70d-157">값</span><span class="sxs-lookup"><span data-stu-id="7c70d-157">Value</span></span>  |<span data-ttu-id="7c70d-158">설명</span><span class="sxs-lookup"><span data-stu-id="7c70d-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7c70d-159">0x4</span><span class="sxs-lookup"><span data-stu-id="7c70d-159">0x4</span></span> | <span data-ttu-id="7c70d-160">키를 정의 하는 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7c70d-161">0x8</span><span class="sxs-lookup"><span data-stu-id="7c70d-161">0x8</span></span> | <span data-ttu-id="7c70d-162">반환 속성 이름만 개체 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="7c70d-163">그룹 3 플래그</span><span class="sxs-lookup"><span data-stu-id="7c70d-163">Group 3 flags</span></span> |<span data-ttu-id="7c70d-164">값</span><span class="sxs-lookup"><span data-stu-id="7c70d-164">Value</span></span>  |<span data-ttu-id="7c70d-165">설명</span><span class="sxs-lookup"><span data-stu-id="7c70d-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7c70d-166">0x10</span><span class="sxs-lookup"><span data-stu-id="7c70d-166">0x10</span></span> | <span data-ttu-id="7c70d-167">가장 많이 파생 된 클래스에 속하는 속성 이름이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="7c70d-168">부모 클래스에서 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7c70d-169">0x20</span><span class="sxs-lookup"><span data-stu-id="7c70d-169">0x20</span></span> | <span data-ttu-id="7c70d-170">부모 클래스에 속하는 속성 이름이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7c70d-171">0 x 30</span><span class="sxs-lookup"><span data-stu-id="7c70d-171">0x30</span></span> | <span data-ttu-id="7c70d-172">시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7c70d-173">0x40</span><span class="sxs-lookup"><span data-stu-id="7c70d-173">0x40</span></span> | <span data-ttu-id="7c70d-174">비 시스템 속성의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="7c70d-175">함수는 항상 새 할당 `SAFEARRAY` 반환 하는 경우 `WBEM_S_NO_ERROR`, 및 `pstrNames` 항상 가리키면로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="7c70d-176">속성이 지정된 된 필터와 일치 하는 경우 반환 되는 배열에서 0 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="7c70d-177">함수가 아닌 다른 값을 반환 하는 경우 `WBM_S_NO_ERROR`, 새 `SAFEARRAY` 구조 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="7c70d-178">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c70d-178">Requirements</span></span>  
 <span data-ttu-id="7c70d-179">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c70d-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c70d-180">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7c70d-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7c70d-181">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c70d-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c70d-182">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c70d-182">See also</span></span>  
[<span data-ttu-id="7c70d-183">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="7c70d-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
