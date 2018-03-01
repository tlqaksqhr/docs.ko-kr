---
title: "EndMethodEnumeration 함수 (관리 되지 않는 API 참조)"
description: "EndMethodEnumeration 함수 메서드 열거형 시퀀스를 종료합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1379adbce449ac3255c359249b0296da96a659a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="76618-103">EndMethodEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="76618-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="76618-104">에 대 한 호출을 시작 하는 열거형 시퀀스를 마칩니다.는 [BeginMethodEnumeration 함수](beginmethodenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76618-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="76618-105">구문</span><span class="sxs-lookup"><span data-stu-id="76618-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="76618-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76618-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="76618-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76618-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="76618-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="76618-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="76618-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="76618-109">Return value</span></span>

<span data-ttu-id="76618-110">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="76618-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="76618-111">상수</span><span class="sxs-lookup"><span data-stu-id="76618-111">Constant</span></span>  |<span data-ttu-id="76618-112">값</span><span class="sxs-lookup"><span data-stu-id="76618-112">Value</span></span>  |<span data-ttu-id="76618-113">설명</span><span class="sxs-lookup"><span data-stu-id="76618-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="76618-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="76618-114">0x8004101d</span></span> | <span data-ttu-id="76618-115">내부 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76618-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="76618-116">0</span><span class="sxs-lookup"><span data-stu-id="76618-116">0</span></span> | <span data-ttu-id="76618-117">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76618-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="76618-118">설명</span><span class="sxs-lookup"><span data-stu-id="76618-118">Remarks</span></span>

<span data-ttu-id="76618-119">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="76618-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="76618-120">호출자에 게 사용 하 여 열거형 시퀀스를 시작 [BeginMethodEnumeration 함수](beginmethodenumeration.md)를 호출 하 여 [NextMethod 함수](nextmethod.md )메서드가 반환 될 때까지 `WBEM_S_NO_MORE_DATA`합니다.</span><span class="sxs-lookup"><span data-stu-id="76618-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="76618-121">호출자가 호출 하 여 시퀀스를 필요에 따라 완료 `EndMethodEnumeration`합니다.</span><span class="sxs-lookup"><span data-stu-id="76618-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="76618-122">호출자에 게 해지할 수 있습니다 열거형 초기 호출 하 여 `EndMethodEnumeration` 언제 든 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="76618-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="76618-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76618-123">Requirements</span></span>  
 <span data-ttu-id="76618-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76618-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76618-125">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="76618-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="76618-126">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="76618-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76618-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76618-127">See also</span></span>  
[<span data-ttu-id="76618-128">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="76618-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
