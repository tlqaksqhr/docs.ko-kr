---
title: "복제 함수 (관리 되지 않는 API 참조)"
description: "복제본 함수는 현재 항목의 전체 복제본으로 새 개체를 반환 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 270150bb674ee7f9a71cf28008c663e3b833600d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clone-function"></a><span data-ttu-id="52019-103">복제 함수</span><span class="sxs-lookup"><span data-stu-id="52019-103">Clone function</span></span>
<span data-ttu-id="52019-104">새 개체는 현재 개체의 전체 복제를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52019-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="52019-105">구문</span><span class="sxs-lookup"><span data-stu-id="52019-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="52019-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52019-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="52019-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52019-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="52019-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="52019-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="52019-109">[out] 완료 된 새 개체의 한 가지 `ptr`합니다.</span><span class="sxs-lookup"><span data-stu-id="52019-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="52019-110">이 인수 수 없습니다 `null` 현재 개체의 복사본을 수신 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="52019-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="52019-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="52019-111">Return value</span></span>

<span data-ttu-id="52019-112">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="52019-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="52019-113">상수</span><span class="sxs-lookup"><span data-stu-id="52019-113">Constant</span></span>  |<span data-ttu-id="52019-114">값</span><span class="sxs-lookup"><span data-stu-id="52019-114">Value</span></span>  |<span data-ttu-id="52019-115">설명</span><span class="sxs-lookup"><span data-stu-id="52019-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="52019-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="52019-116">0x80041001</span></span> | <span data-ttu-id="52019-117">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="52019-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="52019-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="52019-118">0x80041008</span></span> | <span data-ttu-id="52019-119">`null`매개 변수로 지정 된이 사용법에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52019-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="52019-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="52019-120">0x80041006</span></span> | <span data-ttu-id="52019-121">메모리가 부족 하 여 개체를 복제에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52019-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="52019-122">0</span><span class="sxs-lookup"><span data-stu-id="52019-122">0</span></span> | <span data-ttu-id="52019-123">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="52019-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="52019-124">설명</span><span class="sxs-lookup"><span data-stu-id="52019-124">Remarks</span></span>

<span data-ttu-id="52019-125">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="52019-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="52019-126">복제 된 개체는는 COM 개체에는 참조 횟수가 1입니다.</span><span class="sxs-lookup"><span data-stu-id="52019-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="52019-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52019-127">Requirements</span></span>  
 <span data-ttu-id="52019-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52019-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52019-129">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="52019-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="52019-130">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="52019-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52019-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52019-131">See also</span></span>  
[<span data-ttu-id="52019-132">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="52019-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
