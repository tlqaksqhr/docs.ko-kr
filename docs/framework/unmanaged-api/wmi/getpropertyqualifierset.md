---
title: "GetPropertyQualifierSet 함수 (관리 되지 않는 API 참조)"
description: "GetPropertyQualifierSet 함수 속성에 대해 설정할 한정자를 검색 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ca2981c8833abaafd5d206b66d6e91f34e2c91d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="f1dc5-103">GetPropertyQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="f1dc5-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="f1dc5-104">특정 속성에 대해 설정할 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f1dc5-105">구문</span><span class="sxs-lookup"><span data-stu-id="f1dc5-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="f1dc5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1dc5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f1dc5-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f1dc5-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="f1dc5-109">[in] 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-109">[in] The property  name.</span></span> <span data-ttu-id="f1dc5-110">`wszProperty`유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="f1dc5-111">[out] 속성의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="f1dc5-112">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f1dc5-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="f1dc5-113">오류가 발생 하는 경우 새 개체가 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f1dc5-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="f1dc5-114">Return value</span></span>

<span data-ttu-id="f1dc5-115">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="f1dc5-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f1dc5-116">상수</span><span class="sxs-lookup"><span data-stu-id="f1dc5-116">Constant</span></span>  |<span data-ttu-id="f1dc5-117">값</span><span class="sxs-lookup"><span data-stu-id="f1dc5-117">Value</span></span>  |<span data-ttu-id="f1dc5-118">설명</span><span class="sxs-lookup"><span data-stu-id="f1dc5-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="f1dc5-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="f1dc5-119">0x80041001</span></span> | <span data-ttu-id="f1dc5-120">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="f1dc5-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f1dc5-121">0x80041002</span></span> | <span data-ttu-id="f1dc5-122">지정된 된 메서드는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f1dc5-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f1dc5-123">0x80041006</span></span> | <span data-ttu-id="f1dc5-124">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f1dc5-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f1dc5-125">0x80041008</span></span> | <span data-ttu-id="f1dc5-126">매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="f1dc5-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="f1dc5-127">0x80041030</span></span> | <span data-ttu-id="f1dc5-128">함수는 시스템 속성의 한정자를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f1dc5-129">0</span><span class="sxs-lookup"><span data-stu-id="f1dc5-129">0</span></span> | <span data-ttu-id="f1dc5-130">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f1dc5-131">설명</span><span class="sxs-lookup"><span data-stu-id="f1dc5-131">Remarks</span></span>

<span data-ttu-id="f1dc5-132">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="f1dc5-133">이 함수에 대 한 호출에는 현재 개체는 CIM 클래스 정의 하는 경우에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="f1dc5-134">조작 메서드를 사용할 수 없기 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 ponters 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="f1dc5-135">각 메서드에 자체 한정자 있을 수 있으므로 [IWbemQualifierSet 포인터](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 호출자 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="f1dc5-136">함수를 반환 하는 시스템 속성 한정자가 없으므로 `WBEM_E_SYSTEM_PROPERTY` 획득 하려고 하는 경우는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 시스템 속성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1dc5-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1dc5-137">Requirements</span></span>  
<span data-ttu-id="f1dc5-138">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1dc5-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1dc5-139">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f1dc5-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f1dc5-140">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1dc5-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1dc5-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1dc5-141">See also</span></span>  
[<span data-ttu-id="f1dc5-142">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f1dc5-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
