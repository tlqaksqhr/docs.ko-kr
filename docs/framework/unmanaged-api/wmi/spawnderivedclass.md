---
title: "SpawnDerivedClass 함수 (관리 되지 않는 API 참조)"
description: "SpawnDerivedClass 함수는 개체에서 파생 된 새 개체를 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16f9a762c87e1e181202739b70cd978a80864f04
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="1f86c-103">SpawnDerivedClass 함수</span><span class="sxs-lookup"><span data-stu-id="1f86c-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="1f86c-104">지정된 된 개체에서 새로 파생된 클래스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1f86c-105">구문</span><span class="sxs-lookup"><span data-stu-id="1f86c-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="1f86c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f86c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1f86c-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1f86c-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1f86c-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="1f86c-109">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-109">[in] Reserved.</span></span> <span data-ttu-id="1f86c-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="1f86c-111">[out] 새 클래스 정의 개체에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="1f86c-112">오류가 발생 하는 경우 새 개체는 되지 반환 하 고 `ppNewClass` 은 왼쪽 수정 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="1f86c-113">해당 값은 수 없음 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1f86c-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f86c-114">Return value</span></span>

<span data-ttu-id="1f86c-115">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="1f86c-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1f86c-116">상수</span><span class="sxs-lookup"><span data-stu-id="1f86c-116">Constant</span></span>  |<span data-ttu-id="1f86c-117">값</span><span class="sxs-lookup"><span data-stu-id="1f86c-117">Value</span></span>  |<span data-ttu-id="1f86c-118">설명</span><span class="sxs-lookup"><span data-stu-id="1f86c-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1f86c-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="1f86c-119">0x80041001</span></span> | <span data-ttu-id="1f86c-120">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="1f86c-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="1f86c-121">0x80041016</span></span> | <span data-ttu-id="1f86c-122">클래스는 인스턴스를 생성 하는 등의 잘못 된 작업을 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="1f86c-123">완전히 분리 되지 않은 원본 클래스 정의 되었거나 Windows 관리 등록 되므로 새로 파생 된 클래스는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1f86c-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1f86c-124">0x80041006</span></span> | <span data-ttu-id="1f86c-125">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1f86c-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1f86c-126">0x80041008</span></span> | <span data-ttu-id="1f86c-127">`ppNewClass`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="1f86c-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1f86c-128">0</span><span class="sxs-lookup"><span data-stu-id="1f86c-128">0</span></span> | <span data-ttu-id="1f86c-129">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1f86c-130">설명</span><span class="sxs-lookup"><span data-stu-id="1f86c-130">Remarks</span></span>

<span data-ttu-id="1f86c-131">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1f86c-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1f86c-132">`ptr`생성 된 개체의 부모 클래스를 클래스 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="1f86c-133">반환 된 개체가 현재 개체의 하위 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="1f86c-134">반환 되는 새 개체 `ppNewClass` 현재 개체의 하위 클래스는 자동으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="1f86c-135">이 동작을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="1f86c-136">서브 클래스 (파생된 클래스)을 만들 수 있는 다른 메서드가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f86c-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f86c-137">Requirements</span></span>  
 <span data-ttu-id="1f86c-138">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f86c-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f86c-139">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1f86c-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1f86c-140">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f86c-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f86c-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f86c-141">See also</span></span>  
[<span data-ttu-id="1f86c-142">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="1f86c-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
