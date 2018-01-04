---
title: "GetMethod 함수 (관리 되지 않는 API 참조)"
description: "GetMethod 함수는 메서드에 대 한 정보를 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethod
helpviewer_keywords: GetMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f22a2dfa7aae411cac960cbad2017718df8057e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getmethod-function"></a><span data-ttu-id="4f65a-103">GetMethod 함수</span><span class="sxs-lookup"><span data-stu-id="4f65a-103">GetMethod function</span></span>
<span data-ttu-id="4f65a-104">지정 된 메서드에 대 한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4f65a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4f65a-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="4f65a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f65a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4f65a-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4f65a-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4f65a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="4f65a-109">[in] 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-109">[in] The method name.</span></span> <span data-ttu-id="4f65a-110">이 매개 변수 여야 `null` 유효한를 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="4f65a-111">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-111">[in] Reserved.</span></span> <span data-ttu-id="4f65a-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="4f65a-113">[out] 주소에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 메서드에 paramteers 나타내는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4f65a-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="4f65a-114">이 매개 변수는로 설정 되어 있으면 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="4f65a-115">[out] 주소에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 메서드에 out 매개 변수를 나타내는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4f65a-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="4f65a-116">이 매개 변수는로 설정 되어 있으면 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4f65a-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="4f65a-117">Return value</span></span>

<span data-ttu-id="4f65a-118">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="4f65a-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4f65a-119">상수</span><span class="sxs-lookup"><span data-stu-id="4f65a-119">Constant</span></span>  |<span data-ttu-id="4f65a-120">값</span><span class="sxs-lookup"><span data-stu-id="4f65a-120">Value</span></span>  |<span data-ttu-id="4f65a-121">설명</span><span class="sxs-lookup"><span data-stu-id="4f65a-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4f65a-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4f65a-122">0x80041002</span></span> | <span data-ttu-id="4f65a-123">지정된 된 속성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4f65a-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4f65a-124">0x80041006</span></span> | <span data-ttu-id="4f65a-125">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4f65a-126">0</span><span class="sxs-lookup"><span data-stu-id="4f65a-126">0</span></span> | <span data-ttu-id="4f65a-127">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4f65a-128">설명</span><span class="sxs-lookup"><span data-stu-id="4f65a-128">Remarks</span></span>

<span data-ttu-id="4f65a-129">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4f65a-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="4f65a-130">Windows 관리에서 설정할 수는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 에 대 한 포인터 `null` 메서드 매개 변수가 없는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="4f65a-131">`ppInSignature` 및 `ppOutSignature` in 및 out 매개 변수를 각각 속성에 설명 된 `IWbemClassObject` 시스템 클래스의 인스턴스 [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="4f65a-132">속성에 `ppInsignature` 이름은 **Param***n*여기서  *n*  (예: 메서드 시그니처의 매개 변수의 위치 으로 `Param1`, `Param2`등.).</span><span class="sxs-lookup"><span data-stu-id="4f65a-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="4f65a-133">속성에 `ppOutSignature` 라고도 **Param***n*, 반환 값은 이름이 고 **ReturnValue**합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="4f65a-134">자세한 내용 및 예제에 대 한 참조 [IWbemClassObject::GetMethod 메서드](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="4f65a-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f65a-135">Requirements</span></span>  
<span data-ttu-id="4f65a-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f65a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f65a-137">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4f65a-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4f65a-138">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4f65a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f65a-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f65a-139">See also</span></span>  
[<span data-ttu-id="4f65a-140">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="4f65a-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
