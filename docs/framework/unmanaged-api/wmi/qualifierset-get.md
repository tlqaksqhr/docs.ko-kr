---
title: "QualifierSet_Get 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_Get 함수는 명명 된 한정자를 가져옵니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93ba4e59dda4806931ba085f8c63b63a1d8bd797
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="4de83-103">QualifierSet_Get 함수</span><span class="sxs-lookup"><span data-stu-id="4de83-103">QualifierSet_Get function</span></span>
<span data-ttu-id="4de83-104">지정된 된 명명 된 한정자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4de83-105">구문</span><span class="sxs-lookup"><span data-stu-id="4de83-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4de83-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4de83-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="4de83-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="4de83-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4de83-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="4de83-109">[in] 해당 값이 요청 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="4de83-110">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-110">[in] Reserved.</span></span> <span data-ttu-id="4de83-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="4de83-112">[out] 성공 하면 올바른 형식 및 한정자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="4de83-113">함수가 실패 하면는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="4de83-114">이 매개 변수가 `null`, 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="4de83-115">[out] 요청 된 한정자에 대 한 한정자 버전 비트를 수신 하는 LONG에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="4de83-116">버전 정보는 원하지 않을 경우이 매개 변수 수 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4de83-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="4de83-117">Return value</span></span>

<span data-ttu-id="4de83-118">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="4de83-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4de83-119">상수</span><span class="sxs-lookup"><span data-stu-id="4de83-119">Constant</span></span>  |<span data-ttu-id="4de83-120">값</span><span class="sxs-lookup"><span data-stu-id="4de83-120">Value</span></span>  |<span data-ttu-id="4de83-121">설명</span><span class="sxs-lookup"><span data-stu-id="4de83-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4de83-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4de83-122">0x80041008</span></span> | <span data-ttu-id="4de83-123">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4de83-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4de83-124">0x80041002</span></span> | <span data-ttu-id="4de83-125">지정된 된 한정자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4de83-126">0</span><span class="sxs-lookup"><span data-stu-id="4de83-126">0</span></span> | <span data-ttu-id="4de83-127">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4de83-128">설명</span><span class="sxs-lookup"><span data-stu-id="4de83-128">Remarks</span></span>

<span data-ttu-id="4de83-129">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4de83-129">This function wraps a call to the [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4de83-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4de83-130">Requirements</span></span>  
 <span data-ttu-id="4de83-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4de83-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4de83-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4de83-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4de83-133">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4de83-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de83-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4de83-134">See also</span></span>  
[<span data-ttu-id="4de83-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="4de83-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
