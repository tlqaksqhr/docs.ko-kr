---
title: "QualifierSet_Put 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_Put 함수는 명명된 된 한정자 및 값을 씁니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bf5c6dbf0f707942d58f4d7cf155636f0532724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="89e6f-103">QualifierSet_Put 함수</span><span class="sxs-lookup"><span data-stu-id="89e6f-103">QualifierSet_Put function</span></span>
<span data-ttu-id="89e6f-104">명명 된 한정자 및 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="89e6f-105">새 한정자 이름이 동일한 이전 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="89e6f-106">한정자가 없는 경우 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="89e6f-107">구문</span><span class="sxs-lookup"><span data-stu-id="89e6f-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="89e6f-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89e6f-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="89e6f-109">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="89e6f-110">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="89e6f-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="89e6f-111">[in] 쓸 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="89e6f-112">`pVal`[in] 에 대 한 포인터를 올바른 `VARIANT` 쓰려고 한정자를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="89e6f-113">이 매개 변수 여야 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="89e6f-114">`lFlavor`[in] 이 한정자에 대 한 원하는 한정자 버전을 정의 하는 다음 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="89e6f-115">기본값은 `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="89e6f-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="89e6f-116">상수</span><span class="sxs-lookup"><span data-stu-id="89e6f-116">Constant</span></span>  |<span data-ttu-id="89e6f-117">값</span><span class="sxs-lookup"><span data-stu-id="89e6f-117">Value</span></span>  |<span data-ttu-id="89e6f-118">설명</span><span class="sxs-lookup"><span data-stu-id="89e6f-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="89e6f-119">0</span><span class="sxs-lookup"><span data-stu-id="89e6f-119">0</span></span> | <span data-ttu-id="89e6f-120">파생된 클래스 또는 인스턴스가 한정자를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="89e6f-121">**이것이 기본값입니다.**</span><span class="sxs-lookup"><span data-stu-id="89e6f-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="89e6f-122">1</span><span class="sxs-lookup"><span data-stu-id="89e6f-122">1</span></span> | <span data-ttu-id="89e6f-123">한정자가 인스턴스로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="89e6f-124">2</span><span class="sxs-lookup"><span data-stu-id="89e6f-124">2</span></span> | <span data-ttu-id="89e6f-125">한정자는 파생된 클래스에 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="89e6f-126">' WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="89e6f-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="89e6f-127">0x10</span><span class="sxs-lookup"><span data-stu-id="89e6f-127">0x10</span></span> | <span data-ttu-id="89e6f-128">한정자를 파생된 클래스 또는 인스턴스에서 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="89e6f-129">' WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="89e6f-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="89e6f-130">0x80</span><span class="sxs-lookup"><span data-stu-id="89e6f-130">0x80</span></span> | <span data-ttu-id="89e6f-131">한정자도 지역화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="89e6f-132">반환 값</span><span class="sxs-lookup"><span data-stu-id="89e6f-132">Return value</span></span>

<span data-ttu-id="89e6f-133">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="89e6f-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="89e6f-134">상수</span><span class="sxs-lookup"><span data-stu-id="89e6f-134">Constant</span></span>  |<span data-ttu-id="89e6f-135">값</span><span class="sxs-lookup"><span data-stu-id="89e6f-135">Value</span></span>  |<span data-ttu-id="89e6f-136">설명</span><span class="sxs-lookup"><span data-stu-id="89e6f-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="89e6f-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="89e6f-137">0x8004101f</span></span> | <span data-ttu-id="89e6f-138">잘못 지정 하려고 했습니다.는 **키** 키가 될 수 없는 속성에 대 한 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="89e6f-139">키가 지정 되어 c om; 개체에 대 한 어셈블리 정의 및 인스턴스 단위로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="89e6f-140">0x80041008</span><span class="sxs-lookup"><span data-stu-id="89e6f-140">0x80041008</span></span> | <span data-ttu-id="89e6f-141">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="89e6f-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="89e6f-142">0x80041029</span></span> | <span data-ttu-id="89e6f-143">`pVal` 매개 변수가 올바른 한정자 형식이 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="89e6f-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="89e6f-144">0x8004101a</span></span> | <span data-ttu-id="89e6f-145">호출할 수 없으면는 `QualifierSet_Put` 메서드 한정자를 소유 하는 개체는 허용 하지 않으므로 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="89e6f-146">0</span><span class="sxs-lookup"><span data-stu-id="89e6f-146">0</span></span> | <span data-ttu-id="89e6f-147">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="89e6f-148">설명</span><span class="sxs-lookup"><span data-stu-id="89e6f-148">Remarks</span></span>

<span data-ttu-id="89e6f-149">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="89e6f-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="89e6f-150">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89e6f-150">Requirements</span></span>  
 <span data-ttu-id="89e6f-151">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89e6f-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e6f-152">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="89e6f-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="89e6f-153">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89e6f-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e6f-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89e6f-154">See also</span></span>  
[<span data-ttu-id="89e6f-155">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="89e6f-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
