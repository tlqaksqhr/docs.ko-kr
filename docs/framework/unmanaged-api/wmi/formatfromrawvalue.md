---
title: "FormatFromRawValue 함수 (관리 되지 않는 API 참조)"
description: "FormatFromRawValue 함수 원시 성능 데이터를 지정된 된 형식으로 변환합니다."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: FormatFromRawValue
api_location: PerfCounter.dll
api_type: DLLExport
f1_keywords: FormatFromRawValue
helpviewer_keywords: FormatFromRawValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3daa89ec0b40bb9c08898ecd682f05f0f0ce09a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="70bc6-103">FormatFromRawValue 함수</span><span class="sxs-lookup"><span data-stu-id="70bc6-103">FormatFromRawValue function</span></span>
<span data-ttu-id="70bc6-104">시간 기반 형식 변환 되 면 지정된 된 형식으로 원시 성능 데이터 값을 하나 또는 두 개의 원시 성능 데이터 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="70bc6-105">구문</span><span class="sxs-lookup"><span data-stu-id="70bc6-105">Syntax</span></span>  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a><span data-ttu-id="70bc6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70bc6-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="70bc6-107">[in] 카운터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-107">[in] The counter type.</span></span> <span data-ttu-id="70bc6-108">목록이 카운터 형식에 대 한 참조 [WMI 성능 카운터 형식](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-108">For a list of counter types, see [WMI Performance Counter Types](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx).</span></span> <span data-ttu-id="70bc6-109">`dwCounterType`임의의 형식일 수 있습니다 카운터를 제외 하 고 `PERF_LARGE_RAW_FRACTION` 및 `PERF_LARGE_RAW_BASE`합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="70bc6-110">[in] 원시 성능 데이터를 변환할 대상 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="70bc6-111">다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-111">It can be one of the following values:</span></span>

|<span data-ttu-id="70bc6-112">상수</span><span class="sxs-lookup"><span data-stu-id="70bc6-112">Constant</span></span>  |<span data-ttu-id="70bc6-113">값</span><span class="sxs-lookup"><span data-stu-id="70bc6-113">Value</span></span>  |<span data-ttu-id="70bc6-114">설명</span><span class="sxs-lookup"><span data-stu-id="70bc6-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="70bc6-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="70bc6-115">0x00000200</span></span> | <span data-ttu-id="70bc6-116">배정밀도 부동 소수점 값으로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="70bc6-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="70bc6-117">0x00000400</span></span> | <span data-ttu-id="70bc6-118">64 비트 정수로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="70bc6-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="70bc6-119">0x00000100</span></span> | <span data-ttu-id="70bc6-120">32 비트 정수로 계산된 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="70bc6-121">이전 값 중 하나 ORed 다음 배율 플래그 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="70bc6-122">상수</span><span class="sxs-lookup"><span data-stu-id="70bc6-122">Constant</span></span>  |<span data-ttu-id="70bc6-123">값</span><span class="sxs-lookup"><span data-stu-id="70bc6-123">Value</span></span>  |<span data-ttu-id="70bc6-124">설명</span><span class="sxs-lookup"><span data-stu-id="70bc6-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="70bc6-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="70bc6-125">0x00001000</span></span> | <span data-ttu-id="70bc6-126">카운터의 배율 인수는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="70bc6-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="70bc6-127">0x00002000</span></span> | <span data-ttu-id="70bc6-128">1, 000 최종 값을 곱하십시오.</span><span class="sxs-lookup"><span data-stu-id="70bc6-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="70bc6-129">[in] 형식 변환에 필요한 경우 시간 기준에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="70bc6-130">시간 기준 정보가 형식 변환에 대 한 필요가 없는 경우이 매개 변수 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="70bc6-131">`pRawValue1`[in] 에 대 한 포인터는 [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) 원시 성능 값을 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a raw performance value.</span></span>

<span data-ttu-id="70bc6-132">`pRawValue2`[in] 에 대 한 포인터는 [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) 구조를 두 번째 원시 성능 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a second raw performance value.</span></span> <span data-ttu-id="70bc6-133">두 번째 원시 성능 값 필요가 없는 경우이 매개 변수 여야 합니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="70bc6-134">`pFmtValue`[out] 에 대 한 포인터는 [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) 구조체 형식이 지정 된 성능 값입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="70bc6-135">반환 값</span><span class="sxs-lookup"><span data-stu-id="70bc6-135">Return value</span></span>

<span data-ttu-id="70bc6-136">다음 값이이 함수에 의해 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="70bc6-137">상수</span><span class="sxs-lookup"><span data-stu-id="70bc6-137">Constant</span></span>  |<span data-ttu-id="70bc6-138">값</span><span class="sxs-lookup"><span data-stu-id="70bc6-138">Value</span></span>  |<span data-ttu-id="70bc6-139">설명</span><span class="sxs-lookup"><span data-stu-id="70bc6-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="70bc6-140">0</span><span class="sxs-lookup"><span data-stu-id="70bc6-140">0</span></span> | <span data-ttu-id="70bc6-141">함수 호출은 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="70bc6-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="70bc6-142">0xC0000BBD</span></span> | <span data-ttu-id="70bc6-143">필요한 인수가 없거나 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="70bc6-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="70bc6-144">0xC0000BBC</span></span> | <span data-ttu-id="70bc6-145">핸들이 올바른 PDH 개체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="70bc6-146">설명</span><span class="sxs-lookup"><span data-stu-id="70bc6-146">Remarks</span></span>

<span data-ttu-id="70bc6-147">이 함수에 대 한 호출을 래핑하는 [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-147">This function wraps a call to the [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="70bc6-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70bc6-148">Requirements</span></span>  
 <span data-ttu-id="70bc6-149">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70bc6-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70bc6-150">**라이브러리:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="70bc6-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="70bc6-151">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="70bc6-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bc6-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70bc6-152">See also</span></span>  
[<span data-ttu-id="70bc6-153">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="70bc6-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
