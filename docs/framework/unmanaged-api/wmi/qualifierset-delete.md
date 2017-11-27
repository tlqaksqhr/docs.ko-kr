---
title: "QualifierSet_Delete 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_Delete 함수 이름으로 한 한정자를 삭제합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Delete
helpviewer_keywords: QualifierSet_Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9245fc0ee109837249f1f3df400385c117a2f2d7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="e73c1-103">QualifierSet_Delete 함수</span><span class="sxs-lookup"><span data-stu-id="e73c1-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="e73c1-104">이름으로 지정된 된 한정자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e73c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="e73c1-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="e73c1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e73c1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e73c1-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="e73c1-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e73c1-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="e73c1-109">[in] 삭제할 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="e73c1-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e73c1-110">Return value</span></span>

<span data-ttu-id="e73c1-111">이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="e73c1-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e73c1-112">상수</span><span class="sxs-lookup"><span data-stu-id="e73c1-112">Constant</span></span>  |<span data-ttu-id="e73c1-113">값</span><span class="sxs-lookup"><span data-stu-id="e73c1-113">Value</span></span>  |<span data-ttu-id="e73c1-114">설명</span><span class="sxs-lookup"><span data-stu-id="e73c1-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e73c1-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e73c1-115">0x80041008</span></span> | <span data-ttu-id="e73c1-116">`wszName` 매개 변수가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="e73c1-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="e73c1-117">0x80041016</span></span> | <span data-ttu-id="e73c1-118">이 한정자를 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e73c1-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e73c1-119">0x80041002</span></span> | <span data-ttu-id="e73c1-120">지정된 된 한정자를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e73c1-121">0</span><span class="sxs-lookup"><span data-stu-id="e73c1-121">0</span></span> | <span data-ttu-id="e73c1-122">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="e73c1-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="e73c1-123">0x40002</span></span> | <span data-ttu-id="e73c1-124">로컬 재정의 된 삭제 되 고 부모 개체의 원래 한정자 범위를 다시 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e73c1-125">설명</span><span class="sxs-lookup"><span data-stu-id="e73c1-125">Remarks</span></span>

<span data-ttu-id="e73c1-126">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e73c1-126">This function wraps a call to the [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e73c1-127">한정자 전파 규칙으로 인해 특정 한정자 수 있습니다 다른 개체에서 상속 되어 현재 클래스 또는 인스턴스에서 단순히 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="e73c1-128">이 경우에 `QualifierSet_Delete` 메서드 한정자의 원래 상속 된 값을 기본값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="e73c1-129">함수에는 경우 상태 코드 반환 `WBEM_S_RESET_TO_DEFAULT`합니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e73c1-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e73c1-130">Requirements</span></span>  
 <span data-ttu-id="e73c1-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e73c1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e73c1-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e73c1-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e73c1-133">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e73c1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73c1-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e73c1-134">See also</span></span>  
[<span data-ttu-id="e73c1-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="e73c1-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
