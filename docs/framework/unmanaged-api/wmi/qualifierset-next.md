---
title: "QualifierSet_Next 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_Next 함수에는 다음 한정자는 열거형에는 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b66eeab2cba18268b602350c8bc8f489d943309
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="bb577-103">QualifierSet_Next 함수</span><span class="sxs-lookup"><span data-stu-id="bb577-103">QualifierSet_Next function</span></span>
<span data-ttu-id="bb577-104">다음 한정자에 대 한 호출을 시작 하는 열거형에는 검색 된 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bb577-105">구문</span><span class="sxs-lookup"><span data-stu-id="bb577-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="bb577-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb577-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="bb577-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="bb577-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="bb577-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="bb577-109">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-109">[in] Reserved.</span></span> <span data-ttu-id="bb577-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="bb577-111">[out] 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="bb577-112">경우 `null`,이 매개 변수는 무시 되 고, 그렇지 않으면 `pstrName` 해야을 유효한이 가리키지 `BSTR` 또는 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="bb577-113">Null이 아닌 함수는 항상 할당 하는 새 `BSTR` 반환 될 때 `WBEM_S_NO_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="bb577-114">[out] 성공 하면 한정자의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="bb577-115">함수가 실패 하면는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="bb577-116">이 매개 변수가 `null`, 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="bb577-117">[out] 한정자 버전을 수신 하는 LONG에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="bb577-118">버전 정보는 원하지 않을 경우이 매개 변수 수 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="bb577-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="bb577-119">Return value</span></span>

<span data-ttu-id="bb577-120">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="bb577-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bb577-121">상수</span><span class="sxs-lookup"><span data-stu-id="bb577-121">Constant</span></span>  |<span data-ttu-id="bb577-122">값</span><span class="sxs-lookup"><span data-stu-id="bb577-122">Value</span></span>  |<span data-ttu-id="bb577-123">설명</span><span class="sxs-lookup"><span data-stu-id="bb577-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bb577-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bb577-124">0x80041008</span></span> | <span data-ttu-id="bb577-125">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="bb577-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="bb577-126">0x8004101d</span></span> | <span data-ttu-id="bb577-127">호출자에 게 로드 하지 않는 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bb577-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bb577-128">0x80041006</span></span> | <span data-ttu-id="bb577-129">새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="bb577-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="bb577-130">0x40005</span></span> | <span data-ttu-id="bb577-131">열거형에 더 많은 한정자가 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb577-132">0</span><span class="sxs-lookup"><span data-stu-id="bb577-132">0</span></span> | <span data-ttu-id="bb577-133">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bb577-134">설명</span><span class="sxs-lookup"><span data-stu-id="bb577-134">Remarks</span></span>

<span data-ttu-id="bb577-135">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="bb577-135">This function wraps a call to the [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="bb577-136">호출 하 여 `QualifierSet_Next` 반복 함수 반환 될 때까지 모든 한정자를 열거 하는 함수 `WBEM_S_NO_MORE_DATA`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="bb577-137">열거형을 조기에 종료를 호출 하는 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="bb577-138">열거 동안 반환 되는 한정자의 순서는 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb577-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb577-139">Requirements</span></span>  
 <span data-ttu-id="bb577-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb577-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb577-141">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bb577-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bb577-142">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb577-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb577-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb577-143">See also</span></span>  
[<span data-ttu-id="bb577-144">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="bb577-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
