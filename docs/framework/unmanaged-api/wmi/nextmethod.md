---
title: "NextMethod 함수 (관리 되지 않는 API 참조)"
description: "NextMethod 함수 열거형의 다음 메서드를 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b886b3ecbd1d5b5b8d212846b2bd8291fa43909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="nextmethod-function"></a><span data-ttu-id="c0161-103">NextMethod 함수</span><span class="sxs-lookup"><span data-stu-id="c0161-103">NextMethod function</span></span>
<span data-ttu-id="c0161-104">에 대 한 호출으로 시작 하는 열거형의 다음 메서드를 검색 [BeginMethodEnumeration](beginmethodenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c0161-105">구문</span><span class="sxs-lookup"><span data-stu-id="c0161-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="c0161-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0161-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c0161-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c0161-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c0161-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="c0161-109">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-109">[in] Reserved.</span></span> <span data-ttu-id="c0161-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="c0161-111">[out] 가리키는 포인터가 `null` 호출 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="c0161-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="c0161-112">함수가 반환 하는 경우, 새 주소 `BSTR` 메서드 이름이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="c0161-113">[out] 에 대 한 포인터를 받는 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 를 포함 하는 `in` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="c0161-114">[out] 에 대 한 포인터를 받는 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 를 포함 하는 `out` 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c0161-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="c0161-115">Return value</span></span>

<span data-ttu-id="c0161-116">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="c0161-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c0161-117">상수</span><span class="sxs-lookup"><span data-stu-id="c0161-117">Constant</span></span>  |<span data-ttu-id="c0161-118">값</span><span class="sxs-lookup"><span data-stu-id="c0161-118">Value</span></span>  |<span data-ttu-id="c0161-119">설명</span><span class="sxs-lookup"><span data-stu-id="c0161-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="c0161-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c0161-120">0x8004101d</span></span> | <span data-ttu-id="c0161-121">에 대 한 호출이 했습니다는 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c0161-122">0</span><span class="sxs-lookup"><span data-stu-id="c0161-122">0</span></span> | <span data-ttu-id="c0161-123">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="c0161-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="c0161-124">0x40005</span></span> | <span data-ttu-id="c0161-125">열거형에 더 많은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c0161-126">설명</span><span class="sxs-lookup"><span data-stu-id="c0161-126">Remarks</span></span>

<span data-ttu-id="c0161-127">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c0161-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="c0161-128">호출 하 여 열거형 시퀀스를 시작 하는 호출자에 게는 [BeginMethodEnumeration](beginmethodenumeration.md) 함수 및 함수 반환 될 때까지 다음 [NextMethod] 함수를 호출 `WBEM_S_NO_MORE_DATA`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="c0161-129">호출자가 호출 하 여 시퀀스를 완료 하는 필요에 따라 [EndMethodEnumeration](endmethodenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="c0161-130">호출자에 게 해지할 수 있습니다 열거형 초기 호출 하 여 [EndMethodEnumeration](endmethodenumeration.md) 언제 든 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="c0161-131">예</span><span class="sxs-lookup"><span data-stu-id="c0161-131">Example</span></span>

<span data-ttu-id="c0161-132">C + + 예제에 대 한 참조는 [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c0161-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0161-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0161-133">Requirements</span></span>  
 <span data-ttu-id="c0161-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0161-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0161-135">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c0161-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c0161-136">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0161-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0161-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0161-137">See also</span></span>  
[<span data-ttu-id="c0161-138">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c0161-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
