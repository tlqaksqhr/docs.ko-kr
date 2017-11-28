---
title: "Delete 함수 (관리 되지 않는 API 참조)"
description: "Delete 함수는 CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Delete
helpviewer_keywords: Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f32487d2bd59bd76acdc32218c6bb0842de20e87
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="delete-function"></a><span data-ttu-id="8ee4e-103">Delete 함수</span><span class="sxs-lookup"><span data-stu-id="8ee4e-103">Delete function</span></span>
<span data-ttu-id="8ee4e-104">CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8ee4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ee4e-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="8ee4e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ee4e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8ee4e-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8ee4e-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="8ee4e-109">[in] 삭제할 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="8ee4e-110">`wszName`유효한 포인터 여야 합니다. `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8ee4e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8ee4e-111">Return value</span></span>

<span data-ttu-id="8ee4e-112">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="8ee4e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8ee4e-113">상수</span><span class="sxs-lookup"><span data-stu-id="8ee4e-113">Constant</span></span>  |<span data-ttu-id="8ee4e-114">값</span><span class="sxs-lookup"><span data-stu-id="8ee4e-114">Value</span></span>  |<span data-ttu-id="8ee4e-115">설명</span><span class="sxs-lookup"><span data-stu-id="8ee4e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="8ee4e-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="8ee4e-116">0x80041001</span></span> | <span data-ttu-id="8ee4e-117">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="8ee4e-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="8ee4e-118">0x80041016</span></span> | <span data-ttu-id="8ee4e-119">속성을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8ee4e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8ee4e-120">0x80041008</span></span> | <span data-ttu-id="8ee4e-121">`wszzName`이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="8ee4e-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8ee4e-122">0x80041002</span></span> | <span data-ttu-id="8ee4e-123">지정된 된 속성이 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8ee4e-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8ee4e-124">0x80041006</span></span> | <span data-ttu-id="8ee4e-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="8ee4e-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="8ee4e-126">0x8004101c</span></span> | <span data-ttu-id="8ee4e-127">속성은 기본 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="8ee4e-128">속성은 시스템 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8ee4e-129">0</span><span class="sxs-lookup"><span data-stu-id="8ee4e-129">0</span></span> | <span data-ttu-id="8ee4e-130">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="8ee4e-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="8ee4e-131">0x80041030</span></span> | <span data-ttu-id="8ee4e-132">함수는 현재 클래스에 대 한 재정의 기본값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="8ee4e-133">부모 클래스에서이 속성에 대 한 기본값 reactiviated 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="8ee4e-134">설명</span><span class="sxs-lookup"><span data-stu-id="8ee4e-134">Remarks</span></span>

<span data-ttu-id="8ee4e-135">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8ee4e-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ee4e-136">Requirements</span></span>  
 <span data-ttu-id="8ee4e-137">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee4e-138">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8ee4e-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8ee4e-139">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee4e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee4e-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ee4e-140">See also</span></span>  
[<span data-ttu-id="8ee4e-141">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
