---
title: "VerifyClientKey 함수 (관리 되지 않는 API 참조)"
description: "VerifyClientKey 함수 클라이언트 키 올바른 보안 인지 확인 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: VerifyClientKey
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: VerifyClientKey
helpviewer_keywords: VerifyClientKey function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ada878ff8bc430ab2a2d48cac13a81b1f64d39f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="41cc0-103">VerifyClientKey 함수</span><span class="sxs-lookup"><span data-stu-id="41cc0-103">VerifyClientKey function</span></span>
<span data-ttu-id="41cc0-104">클라이언트 키에 올바른 보안 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc0-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="41cc0-105">구문</span><span class="sxs-lookup"><span data-stu-id="41cc0-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="41cc0-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="41cc0-106">Return value</span></span>

<span data-ttu-id="41cc0-107">함수가 성공 하면 반환 값은 `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="41cc0-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="41cc0-108">반환 값은 0이 아닌 오류 코드에 정의 된 함수가 실패 하면 *WinError.h*합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc0-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="41cc0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41cc0-109">Requirements</span></span>  
 <span data-ttu-id="41cc0-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41cc0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cc0-111">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="41cc0-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="41cc0-112">**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41cc0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cc0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41cc0-113">See also</span></span>  
[<span data-ttu-id="41cc0-114">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="41cc0-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
