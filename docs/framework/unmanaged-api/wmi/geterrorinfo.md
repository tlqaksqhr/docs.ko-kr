---
title: "GetErrorInfo 함수 (관리 되지 않는 API 참조)"
description: "GetErrorInfo 함수는 이전 함수 호출에서 오류 정보를 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1bdaa72723855c6688a7c8c7704b958f6196dfd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="8dbce-103">GetErrorInfo 함수</span><span class="sxs-lookup"><span data-stu-id="8dbce-103">GetErrorInfo function</span></span>
<span data-ttu-id="8dbce-104">이전 함수 호출에서 오류 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbce-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8dbce-105">구문</span><span class="sxs-lookup"><span data-stu-id="8dbce-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="8dbce-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="8dbce-106">Return value</span></span>

<span data-ttu-id="8dbce-107">에 대 한 포인터는 [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) 함수 호출에 성공 하면 개체 또는 `null` 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbce-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8dbce-108">설명</span><span class="sxs-lookup"><span data-stu-id="8dbce-108">Remarks</span></span>

<span data-ttu-id="8dbce-109">이 함수에 대 한 호출을 래핑하는 [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8dbce-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8dbce-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8dbce-110">Requirements</span></span>  
 <span data-ttu-id="8dbce-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbce-112">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="8dbce-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="8dbce-113">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbce-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dbce-114">See also</span></span>  
[<span data-ttu-id="8dbce-115">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="8dbce-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
