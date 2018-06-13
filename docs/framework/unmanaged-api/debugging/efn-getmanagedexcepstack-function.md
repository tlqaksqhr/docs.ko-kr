---
title: _EFN_GetManagedExcepStack 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44f3604e3c12cd4b9781876d2d412d942353061e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404156"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="e60f0-102">_EFN_GetManagedExcepStack 함수</span><span class="sxs-lookup"><span data-stu-id="e60f0-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="e60f0-103">관리되는 예외 개체 주소를 제공하면 내부에 포함된 스택 추적의 문자열 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e60f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="e60f0-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e60f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e60f0-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="e60f0-106">[in] 디버깅 중인 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="e60f0-107">[in] 관리 되는 개체 포인터에서 파생 된 <xref:System.Exception>합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="e60f0-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="e60f0-108">szStackString</span></span>  
 <span data-ttu-id="e60f0-109">[out] 반환 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="e60f0-110">[out] 문자열 버퍼에서 사용할 수 있는 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e60f0-111">설명</span><span class="sxs-lookup"><span data-stu-id="e60f0-111">Remarks</span></span>  
 <span data-ttu-id="e60f0-112">관리 되는 코드가 없는 스레드의 현재 컨텍스트에서 함수 0xa0 시설 값 및 오류 코드 0 x 1000 SOS_E_NOMANAGEDCODE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e60f0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e60f0-113">Requirements</span></span>  
 <span data-ttu-id="e60f0-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e60f0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e60f0-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="e60f0-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e60f0-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e60f0-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60f0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e60f0-117">See Also</span></span>  
 [<span data-ttu-id="e60f0-118">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e60f0-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
