---
title: ResetSecurity 함수 (관리 되지 않는 API 참조)
description: ResetSecurity 함수를 현재 스레드에서 가장 토큰을 지정합니다.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31e42b9e39ddb43025e18888572c394d742e38cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457908"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="ab7ec-103">ResetSecurity 함수</span><span class="sxs-lookup"><span data-stu-id="ab7ec-103">ResetSecurity function</span></span>
<span data-ttu-id="ab7ec-104">현재 스레드의에 제공 된 가장 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ab7ec-105">구문</span><span class="sxs-lookup"><span data-stu-id="ab7ec-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="ab7ec-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab7ec-106">Parameters</span></span>

`token`  
<span data-ttu-id="ab7ec-107">[in] 현재 스레드와 연결할 가장 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="ab7ec-108">이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ab7ec-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab7ec-109">Return value</span></span>

<span data-ttu-id="ab7ec-110">함수가 성공 하면 반환 값은 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="ab7ec-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="ab7ec-111">함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="ab7ec-112">확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ab7ec-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab7ec-113">Requirements</span></span>  
 <span data-ttu-id="ab7ec-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab7ec-115">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ab7ec-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ab7ec-116">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ab7ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7ec-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab7ec-117">See also</span></span>  
[<span data-ttu-id="ab7ec-118">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ab7ec-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
