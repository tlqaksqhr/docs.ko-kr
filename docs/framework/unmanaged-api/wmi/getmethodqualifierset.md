---
title: "GetMethodQualifierSet 함수 (관리 되지 않는 API 참조)"
description: "GetMethodQualifierSet 함수 메서드의 한정자 집합을 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2999bef31576cf2bc025868260c2b1782a9b69f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="08616-103">GetMethodQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="08616-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="08616-104">특정 방법에 대해 설정할 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="08616-105">구문</span><span class="sxs-lookup"><span data-stu-id="08616-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="08616-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08616-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="08616-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08616-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="08616-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="08616-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="08616-109">[in] 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08616-109">[in] The method  name.</span></span> <span data-ttu-id="08616-110">`wszMethod`유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="08616-111">[out] 메서드의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="08616-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="08616-112">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="08616-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="08616-113">오류가 발생 하는 경우 새 개체가 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="08616-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="08616-114">Return value</span></span>

<span data-ttu-id="08616-115">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="08616-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="08616-116">상수</span><span class="sxs-lookup"><span data-stu-id="08616-116">Constant</span></span>  |<span data-ttu-id="08616-117">값</span><span class="sxs-lookup"><span data-stu-id="08616-117">Value</span></span>  |<span data-ttu-id="08616-118">설명</span><span class="sxs-lookup"><span data-stu-id="08616-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="08616-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="08616-119">0x80041002</span></span> | <span data-ttu-id="08616-120">지정된 된 메서드는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08616-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="08616-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="08616-121">0x80041008</span></span> | <span data-ttu-id="08616-122">매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="08616-123">0</span><span class="sxs-lookup"><span data-stu-id="08616-123">0</span></span> | <span data-ttu-id="08616-124">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="08616-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="08616-125">설명</span><span class="sxs-lookup"><span data-stu-id="08616-125">Remarks</span></span>

<span data-ttu-id="08616-126">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="08616-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="08616-127">이 함수에 대 한 호출에는 현재 개체는 CIM 클래스 정의 하는 경우에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08616-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="08616-128">조작 메서드를 사용할 수 없기 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 ponters 합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-128">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="08616-129">각 메서드에 자체 한정자 있을 수 있으므로 [IWbemQualifierSet 포인터](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 호출자 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08616-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="08616-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08616-130">Requirements</span></span>  
<span data-ttu-id="08616-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08616-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08616-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="08616-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="08616-133">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08616-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08616-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08616-134">See also</span></span>  
[<span data-ttu-id="08616-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="08616-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
