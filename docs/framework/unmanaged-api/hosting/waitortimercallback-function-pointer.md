---
title: "WAITORTIMERCALLBACK 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAITORTIMERCALLBACK
api_location: mscoree.dll
api_type: COM
f1_keywords: WAITORTIMERCALLBACK
helpviewer_keywords: WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 873d2ff489085ec2a0c37be2feeb3e15f61c9227
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="8774d-102">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="8774d-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="8774d-103">대기를 처리 하는 호스트를 알리는 함수를 가리키는 (<xref:System.Threading.WaitHandle>) 중 하나 신호 되었거나 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8774d-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="8774d-104">이 함수 포인터에서 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8774d-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8774d-105">구문</span><span class="sxs-lookup"><span data-stu-id="8774d-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8774d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8774d-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="8774d-107">[in] 호스트에 의해 정의 된 정보를 포함 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8774d-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="8774d-108">[in] `true` 대기 핸들을 초과 하는 경우 또는 `false` 이 신호를 받은 경우.</span><span class="sxs-lookup"><span data-stu-id="8774d-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8774d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8774d-109">Remarks</span></span>  
 <span data-ttu-id="8774d-110">함수를 `WAITORTIMERCALLBACK` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8774d-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8774d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8774d-111">Requirements</span></span>  
 <span data-ttu-id="8774d-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8774d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8774d-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8774d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8774d-114">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="8774d-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="8774d-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8774d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8774d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8774d-116">See Also</span></span>  
 [<span data-ttu-id="8774d-117">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8774d-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
