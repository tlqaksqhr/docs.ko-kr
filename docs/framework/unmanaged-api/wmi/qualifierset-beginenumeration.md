---
title: QualifierSet_BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_BeginEnumeration 함수 개체의 한정자의 열거자를 다시 설정합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fac897f743ca452c38282143cdf822b682df1df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460117"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="c7dfa-103">QualifierSet_BeginEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="c7dfa-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="c7dfa-104">열거형의 시작 부분에 있는 개체의 한정자의 열거자를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c7dfa-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7dfa-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="c7dfa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7dfa-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="c7dfa-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="c7dfa-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="c7dfa-109">[in] 플래그 또는에 설명 된 값의 비트 조합은 [주의](#remarks) 열거형에 포함 하려면 한정자를 지정 하는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="c7dfa-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7dfa-110">Return value</span></span>

<span data-ttu-id="c7dfa-111">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="c7dfa-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c7dfa-112">상수</span><span class="sxs-lookup"><span data-stu-id="c7dfa-112">Constant</span></span>  |<span data-ttu-id="c7dfa-113">값</span><span class="sxs-lookup"><span data-stu-id="c7dfa-113">Value</span></span>  |<span data-ttu-id="c7dfa-114">설명</span><span class="sxs-lookup"><span data-stu-id="c7dfa-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c7dfa-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c7dfa-115">0x80041008</span></span> | <span data-ttu-id="c7dfa-116">`lFlags` 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="c7dfa-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c7dfa-117">0x8004101d</span></span> | <span data-ttu-id="c7dfa-118">두 번째 호출으로 `QualifierSet_BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c7dfa-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c7dfa-119">0x80041006</span></span> | <span data-ttu-id="c7dfa-120">새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c7dfa-121">0</span><span class="sxs-lookup"><span data-stu-id="c7dfa-121">0</span></span> | <span data-ttu-id="c7dfa-122">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c7dfa-123">설명</span><span class="sxs-lookup"><span data-stu-id="c7dfa-123">Remarks</span></span>

<span data-ttu-id="c7dfa-124">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="c7dfa-125">모든 개체에는 한정자를 열거 하려면이 메서드를 처음 호출 하기 전에 호출 해야 [QualifierSet_Next](qualifierset-next.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="c7dfa-126">한정자는 열거 순서를 지정 된 열거형에 대해 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="c7dfa-127">로 전달 될 수 있는 플래그는 `lEnumFlags` 에 정의 된 인수는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="c7dfa-128">상수</span><span class="sxs-lookup"><span data-stu-id="c7dfa-128">Constant</span></span>  |<span data-ttu-id="c7dfa-129">값</span><span class="sxs-lookup"><span data-stu-id="c7dfa-129">Value</span></span>  |<span data-ttu-id="c7dfa-130">설명</span><span class="sxs-lookup"><span data-stu-id="c7dfa-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="c7dfa-131">0</span><span class="sxs-lookup"><span data-stu-id="c7dfa-131">0</span></span> | <span data-ttu-id="c7dfa-132">모든 한정자의 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c7dfa-133">0x10</span><span class="sxs-lookup"><span data-stu-id="c7dfa-133">0x10</span></span> | <span data-ttu-id="c7dfa-134">현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="c7dfa-135">속성에 대 한: (재정의 포함), 속성에 특정 한정자만 반환 하 고 클래스 정의에서 이러한 한정자 하지 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c7dfa-136">인스턴스에 대 한: 인스턴스별 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="c7dfa-137">클래스에 대 한: 파생 클래스 beiong 특정 한정자만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="c7dfa-138">0x20</span><span class="sxs-lookup"><span data-stu-id="c7dfa-138">0x20</span></span> | <span data-ttu-id="c7dfa-139">반환이 한정자의 이름만 전파 다른 개체에서입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="c7dfa-140">속성에 대 한:에서 반환 한정자만 전파이 속성에는 클래스 정의 및 속성 자체에서 해당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="c7dfa-141">인스턴스에 대 한: 클래스 정의에서 이러한 한정자만 전파를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="c7dfa-142">클래스에 대 한: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c7dfa-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7dfa-143">Requirements</span></span>  
 <span data-ttu-id="c7dfa-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dfa-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7dfa-145">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c7dfa-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c7dfa-146">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c7dfa-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7dfa-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="c7dfa-147">See also</span></span>  
[<span data-ttu-id="c7dfa-148">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c7dfa-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
