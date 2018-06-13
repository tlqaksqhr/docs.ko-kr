---
title: SetSecurity 함수 (관리 되지 않는 API 참조)
description: SetSecurity 함수는 현재 스레드의 가장 토큰을 검색합니다.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fd354e1103832abee7f634eace3dd6defa8b646
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458753"
---
# <a name="setsecurity-function"></a><span data-ttu-id="20dc1-103">SetSecurity 함수</span><span class="sxs-lookup"><span data-stu-id="20dc1-103">SetSecurity function</span></span>
<span data-ttu-id="20dc1-104">현재 스레드와 연결 된 가장 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="20dc1-105">구문</span><span class="sxs-lookup"><span data-stu-id="20dc1-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="20dc1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20dc1-106">Parameters</span></span>

<span data-ttu-id="20dc1-107">`pNeedToReset` [out] 함수에서 반환에 대 한 포인터를 포함 한 `boolean` 호출 하 여 토큰을 다시 설정할지 여부를 나타내는 [ResetSecurity](resetsecurity.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="20dc1-108">[out] 함수가 반환 될 때 현재 스레드와 연결 된 가장 토큰 핸들에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="20dc1-109">해당 값으로 가능 `null` 현재 스레드와 연결 된 토큰이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="20dc1-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="20dc1-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="20dc1-110">Return value</span></span>

<span data-ttu-id="20dc1-111">함수가 성공 하면 반환 값은 `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="20dc1-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="20dc1-112">함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="20dc1-113">확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="20dc1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20dc1-114">Requirements</span></span>  
 <span data-ttu-id="20dc1-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20dc1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20dc1-116">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="20dc1-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="20dc1-117">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20dc1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20dc1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="20dc1-118">See also</span></span>  
[<span data-ttu-id="20dc1-119">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="20dc1-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
