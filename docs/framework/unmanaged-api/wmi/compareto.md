---
title: CompareTo 함수 (관리 되지 않는 API 참조)
description: CompareTo 함수는 개체를 다른 WMI 개체를 비교합니다.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460410"
---
# <a name="compareto-function"></a><span data-ttu-id="ae487-103">CompareTo 함수</span><span class="sxs-lookup"><span data-stu-id="ae487-103">CompareTo function</span></span>
<span data-ttu-id="ae487-104">다른 Windows 관리 개체에 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ae487-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae487-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="ae487-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae487-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ae487-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ae487-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ae487-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`flags`  
<span data-ttu-id="ae487-109">[in] 비교에 고려해 야 할 개체 특성을 지정 하는 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="ae487-110">참조는 [주의](#remarks) 한 자세 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="ae487-111">[in] 비교할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-111">[in] The object for comparison.</span></span> <span data-ttu-id="ae487-112">`pcompareTo` 유효한 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스이거나 않아야 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-112">`pcompareTo` must be a valid [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ae487-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae487-113">Return value</span></span>

<span data-ttu-id="ae487-114">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="ae487-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ae487-115">상수</span><span class="sxs-lookup"><span data-stu-id="ae487-115">Constant</span></span>  |<span data-ttu-id="ae487-116">값</span><span class="sxs-lookup"><span data-stu-id="ae487-116">Value</span></span>  |<span data-ttu-id="ae487-117">설명</span><span class="sxs-lookup"><span data-stu-id="ae487-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ae487-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="ae487-118">0x80041001</span></span> | <span data-ttu-id="ae487-119">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ae487-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ae487-120">0x80041008</span></span> | <span data-ttu-id="ae487-121">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="ae487-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ae487-122">0x8004101d</span></span> | <span data-ttu-id="ae487-123">두 번째 호출으로 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ae487-124">0</span><span class="sxs-lookup"><span data-stu-id="ae487-124">0</span></span> | <span data-ttu-id="ae487-125">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="ae487-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="ae487-126">0x40003</span></span> | <span data-ttu-id="ae487-127">개체는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="ae487-128">0</span><span class="sxs-lookup"><span data-stu-id="ae487-128">0</span></span> | <span data-ttu-id="ae487-129">개체는 비교 플래그에 따라 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ae487-130">설명</span><span class="sxs-lookup"><span data-stu-id="ae487-130">Remarks</span></span>

<span data-ttu-id="ae487-131">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ae487-131">This function wraps a call to the [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ae487-132">로 전달 될 수 있는 플래그는 `lEnumFlags` 에 정의 된 인수는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="ae487-133">다음 플래그의 비트 조합을 지정 하 여 비교에 사용 되는 개별 특성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="ae487-134">상수</span><span class="sxs-lookup"><span data-stu-id="ae487-134">Constant</span></span>  |<span data-ttu-id="ae487-135">값</span><span class="sxs-lookup"><span data-stu-id="ae487-135">Value</span></span>  |<span data-ttu-id="ae487-136">설명</span><span class="sxs-lookup"><span data-stu-id="ae487-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="ae487-137">2</span><span class="sxs-lookup"><span data-stu-id="ae487-137">2</span></span> | <span data-ttu-id="ae487-138">원본 (서버 및에서 가져온 네임 스페이스)를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="ae487-139">1</span><span class="sxs-lookup"><span data-stu-id="ae487-139">1</span></span> | <span data-ttu-id="ae487-140">모든 한정자를 무시 (포함 하 여 **키** 및 **동적**)</span><span class="sxs-lookup"><span data-stu-id="ae487-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="ae487-141">4</span><span class="sxs-lookup"><span data-stu-id="ae487-141">4</span></span> | <span data-ttu-id="ae487-142">속성의 기본값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-142">Ignore default values of properties.</span></span> <span data-ttu-id="ae487-143">이 플래그는 클래스의 비교에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="ae487-144">0x20</span><span class="sxs-lookup"><span data-stu-id="ae487-144">0x20</span></span> | <span data-ttu-id="ae487-145">한정자 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="ae487-146">이 플래그 여전히 고려 한정자 하지만 특색 전파 규칙 등의 차이 무시 하 고 제한을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="ae487-147">0x10</span><span class="sxs-lookup"><span data-stu-id="ae487-147">0x10</span></span> | <span data-ttu-id="ae487-148">문자열 값을 비교할 때 대/소문자를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="ae487-149">문자열 및 값 한정자에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="ae487-150">속성 이름과 한정자의 비교는 항상이 플래그가 설정 되어 있는지 여부에 관계 없이 대/소문자 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="ae487-151">0x8</span><span class="sxs-lookup"><span data-stu-id="ae487-151">0x8</span></span> | <span data-ttu-id="ae487-152">비교 되는 개체는 동일한 클래스의 인스턴스를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="ae487-153">따라서이 플래그는 인스턴스와 관련 된 정보만 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="ae487-154">이 플래그를 사용 하 여 성능을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="ae487-155">동일한 클래스의 개체가 없는 경우 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="ae487-156">또는 다음과 같이 단일 복합 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="ae487-157">상수</span><span class="sxs-lookup"><span data-stu-id="ae487-157">Constant</span></span>  |<span data-ttu-id="ae487-158">값</span><span class="sxs-lookup"><span data-stu-id="ae487-158">Value</span></span>  |<span data-ttu-id="ae487-159">설명</span><span class="sxs-lookup"><span data-stu-id="ae487-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="ae487-160">0</span><span class="sxs-lookup"><span data-stu-id="ae487-160">0</span></span> | <span data-ttu-id="ae487-161">비교에 사용 된 모든 기능을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ae487-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae487-162">Requirements</span></span>  
 <span data-ttu-id="ae487-163">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae487-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae487-164">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ae487-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ae487-165">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae487-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae487-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae487-166">See also</span></span>  
[<span data-ttu-id="ae487-167">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ae487-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
