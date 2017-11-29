---
title: "QualifierSet_EndEnumeration 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_EndEnumeration 함수는 열거형을 종료 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="306da-103">QualifierSet_EndEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="306da-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="306da-104">열거형에 대 한 호출을 시작한 종료는 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="306da-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="306da-105">구문</span><span class="sxs-lookup"><span data-stu-id="306da-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="306da-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="306da-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="306da-107">[in] 이 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="306da-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="306da-108">[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="306da-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="306da-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="306da-109">Return value</span></span>

<span data-ttu-id="306da-110">이 함수에서 반환 되는 다음 값에 정의 된 *WbemCli.h* 헤더 파일을 정의할 수는 상수로 코드에서:</span><span class="sxs-lookup"><span data-stu-id="306da-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="306da-111">상수</span><span class="sxs-lookup"><span data-stu-id="306da-111">Constant</span></span>  |<span data-ttu-id="306da-112">값</span><span class="sxs-lookup"><span data-stu-id="306da-112">Value</span></span>  |<span data-ttu-id="306da-113">설명</span><span class="sxs-lookup"><span data-stu-id="306da-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="306da-114">0</span><span class="sxs-lookup"><span data-stu-id="306da-114">0</span></span> | <span data-ttu-id="306da-115">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="306da-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="306da-116">설명</span><span class="sxs-lookup"><span data-stu-id="306da-116">Remarks</span></span>

<span data-ttu-id="306da-117">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="306da-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="306da-118">이 호출은 권장 되지만 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="306da-118">This call is recommended, but not required.</span></span> <span data-ttu-id="306da-119">즉시 열거와 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="306da-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="306da-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="306da-120">Requirements</span></span>  

<span data-ttu-id="306da-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="306da-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="306da-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="306da-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="306da-123">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="306da-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306da-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="306da-124">See also</span></span>  
[<span data-ttu-id="306da-125">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="306da-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
