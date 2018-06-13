---
title: GetQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetQualifierSet 함수 한정자는 클래스 또는 인스턴스를 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b50befa4346e17048598afd3d018dbde2fe8572
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458564"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="ac121-103">GetQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="ac121-103">GetQualifierSet function</span></span>
<span data-ttu-id="ac121-104">클래스 인스턴스 또는 클래스 정의 대 한 한정자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ac121-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac121-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="ac121-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac121-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ac121-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ac121-108">[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ac121-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="ac121-109">[out] 클래스 개체의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="ac121-110">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="ac121-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="ac121-111">오류가 발생 하 고 새 개체가 반환 되지 않으면 포인터가 그대로 사용 하는 경우 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ac121-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac121-112">Return value</span></span>

<span data-ttu-id="ac121-113">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="ac121-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac121-114">상수</span><span class="sxs-lookup"><span data-stu-id="ac121-114">Constant</span></span>  |<span data-ttu-id="ac121-115">값</span><span class="sxs-lookup"><span data-stu-id="ac121-115">Value</span></span>  |<span data-ttu-id="ac121-116">설명</span><span class="sxs-lookup"><span data-stu-id="ac121-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ac121-117">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="ac121-117">0x80041001</span></span> | <span data-ttu-id="ac121-118">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ac121-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ac121-119">0x80041002</span></span> | <span data-ttu-id="ac121-120">지정된 된 메서드는 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ac121-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ac121-121">0x80041006</span></span> | <span data-ttu-id="ac121-122">작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ac121-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ac121-123">0x80041008</span></span> | <span data-ttu-id="ac121-124">매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ac121-125">0</span><span class="sxs-lookup"><span data-stu-id="ac121-125">0</span></span> | <span data-ttu-id="ac121-126">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ac121-127">설명</span><span class="sxs-lookup"><span data-stu-id="ac121-127">Remarks</span></span>

<span data-ttu-id="ac121-128">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ac121-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="ac121-129">[IWbemQualifierSet 포인터](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 호출자 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="ac121-130">이러한 추가, 편집 또는 삭제 된 한정자는 전체 인스턴스 또는 클래스 정의에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac121-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac121-131">Requirements</span></span>  
<span data-ttu-id="ac121-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac121-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac121-133">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ac121-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ac121-134">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac121-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac121-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac121-135">See also</span></span>  
[<span data-ttu-id="ac121-136">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ac121-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
