---
title: "QualifierSet_GetNames 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_GetNames 함수 개체 또는 속성에서 한정자의 이름을 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6077b448c2644f68d12679cf208ee921c2af119a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="1e078-103">QualifierSet_GetNames 함수</span><span class="sxs-lookup"><span data-stu-id="1e078-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="1e078-104">현재 개체 또는 속성에서 사용할 수 있는 특정 한정자 또는 모든 한정자의 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1e078-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e078-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="1e078-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e078-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="1e078-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1e078-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1e078-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="1e078-109">[in] 다음 플래그 또는 열거형에 포함 하는 이름을 지정 하는 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="1e078-110">상수</span><span class="sxs-lookup"><span data-stu-id="1e078-110">Constant</span></span>  |<span data-ttu-id="1e078-111">값</span><span class="sxs-lookup"><span data-stu-id="1e078-111">Value</span></span>  |<span data-ttu-id="1e078-112">설명</span><span class="sxs-lookup"><span data-stu-id="1e078-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="1e078-113">0</span><span class="sxs-lookup"><span data-stu-id="1e078-113">0</span></span> | <span data-ttu-id="1e078-114">모든 한정자의 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="1e078-115">0x10</span><span class="sxs-lookup"><span data-stu-id="1e078-115">0x10</span></span> | <span data-ttu-id="1e078-116">현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="1e078-117">속성에 대 한: (재정의 포함), 속성에 특정 한정자만 반환 하 고 클래스 정의에서 이러한 한정자 하지 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="1e078-118">인스턴스에 대 한: 인스턴스별 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="1e078-119">클래스에 대 한: 파생 클래스 beiong 특정 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="1e078-120">0x20</span><span class="sxs-lookup"><span data-stu-id="1e078-120">0x20</span></span> | <span data-ttu-id="1e078-121">반환이 한정자의 이름만 전파 다른 개체에서입니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="1e078-122">속성에 대 한:에서 반환 한정자만 전파이 속성에는 클래스 정의 및 속성 자체에서 해당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="1e078-123">인스턴스에 대 한: 클래스 정의에서 이러한 한정자만 전파를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="1e078-124">클래스에 대 한: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="1e078-125">`pstrNames`[out] 새 `SAFEARRAY` 요청한 이름이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="1e078-126">배열의 요소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-126">The array can have 0 elements.</span></span> <span data-ttu-id="1e078-127">오류가 발생할 때, 새 `SAFEARRAY` 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e078-128">반환 값</span><span class="sxs-lookup"><span data-stu-id="1e078-128">Return value</span></span>

<span data-ttu-id="1e078-129">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="1e078-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1e078-130">상수</span><span class="sxs-lookup"><span data-stu-id="1e078-130">Constant</span></span>  |<span data-ttu-id="1e078-131">값</span><span class="sxs-lookup"><span data-stu-id="1e078-131">Value</span></span>  |<span data-ttu-id="1e078-132">설명</span><span class="sxs-lookup"><span data-stu-id="1e078-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1e078-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1e078-133">0x80041008</span></span> | <span data-ttu-id="1e078-134">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1e078-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1e078-135">0x80041006</span></span> | <span data-ttu-id="1e078-136">새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1e078-137">0</span><span class="sxs-lookup"><span data-stu-id="1e078-137">0</span></span> | <span data-ttu-id="1e078-138">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1e078-139">설명</span><span class="sxs-lookup"><span data-stu-id="1e078-139">Remarks</span></span>

<span data-ttu-id="1e078-140">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1e078-140">This function wraps a call to the [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1e078-141">검색 한 후 한정자 이름, 액세스할 수 있습니다 각 한정자 이름으로 호출 하 여는 [QualifierSet_Get](qualifierset-get.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="1e078-142">따라서 0 한정자가 지정된 된 개체에 대 한 오류가 아닙니다의 문자열 수 `pstrNames` 반환 두 일 수 있습니다, 함수 반환 하는 경우에 `WBEM_S_NO_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e078-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e078-143">Requirements</span></span>  
 <span data-ttu-id="1e078-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e078-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e078-145">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1e078-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1e078-146">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1e078-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e078-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e078-147">See also</span></span>  
[<span data-ttu-id="1e078-148">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1e078-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
