---
title: "GetPropertyHandle 함수 (관리 되지 않는 API 참조)"
description: "GetPropertyHandle 함수는 고유한 핸들 해당 identies 속성을 반환합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="f55e8-103">GetPropertyHandle 함수</span><span class="sxs-lookup"><span data-stu-id="f55e8-103">GetPropertyHandle function</span></span>
<span data-ttu-id="f55e8-104">속성을 식별 하는 고유한 핸들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f55e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="f55e8-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="f55e8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f55e8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f55e8-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f55e8-108">[in] 에 대 한 포인터는 [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f55e8-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="f55e8-109">[in] 속성 이름을 포함 하는 u t f 16으로 인코딩된 characaters의 null로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="f55e8-110">[out] 에 대 한 포인터는 [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) 속성의 CIM 형식을 나타내는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="f55e8-111">[out] 속성 핸들을 포함 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="f55e8-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="f55e8-112">Return value</span></span>

<span data-ttu-id="f55e8-113">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="f55e8-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f55e8-114">상수</span><span class="sxs-lookup"><span data-stu-id="f55e8-114">Constant</span></span>  |<span data-ttu-id="f55e8-115">값</span><span class="sxs-lookup"><span data-stu-id="f55e8-115">Value</span></span>  |<span data-ttu-id="f55e8-116">설명</span><span class="sxs-lookup"><span data-stu-id="f55e8-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f55e8-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f55e8-117">0x80041002</span></span> | <span data-ttu-id="f55e8-118">지정된 된 속성 이름을 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f55e8-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f55e8-119">0x80041008</span></span> | <span data-ttu-id="f55e8-120">매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="f55e8-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="f55e8-121">0x8004100c</span></span> | <span data-ttu-id="f55e8-122">요청 된 속성은 형식이 `CIM_OBJECT` 또는 `CIM_ARRAY`합니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f55e8-123">0</span><span class="sxs-lookup"><span data-stu-id="f55e8-123">0</span></span> | <span data-ttu-id="f55e8-124">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f55e8-125">설명</span><span class="sxs-lookup"><span data-stu-id="f55e8-125">Remarks</span></span>

<span data-ttu-id="f55e8-126">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f55e8-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="f55e8-127">이 핸들을 사용 하 여 속성을 사용 하는 경우 식별 [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) 메서드 읽기 또는 쓰기 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="f55e8-128">이외의 모든 데이터 형식의 속성에 대 한 검색할 수 핸들 `CIM_OBJECT` 및 `CIM_ARRAY`합니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="f55e8-129">클래스의 모든 인 스턴에서 반환 된 핸들 작업.</span><span class="sxs-lookup"><span data-stu-id="f55e8-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="f55e8-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f55e8-130">Requirements</span></span>  
<span data-ttu-id="f55e8-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f55e8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f55e8-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f55e8-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f55e8-133">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f55e8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f55e8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f55e8-134">See also</span></span>  
[<span data-ttu-id="f55e8-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f55e8-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
