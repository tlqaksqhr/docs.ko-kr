---
title: "GetStartupNotificationEvent 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 809f34d265e0a1677d8b7fc78515b20df7353968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="961f6-102">GetStartupNotificationEvent 함수</span><span class="sxs-lookup"><span data-stu-id="961f6-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="961f6-103">지정된 대상 프로세스에 로드 중인 CLR(공용 언어 런타임)에서 신호를 전송할 이벤트 핸들을 만들거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="961f6-104">Syntax</span></span>  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="961f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="961f6-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="961f6-106">[in] CLR 시작 알림을 수신할 대상 프로세스의 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="961f6-107">[out] 시작 시 CLR에서 신호를 전송할 핸들에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="961f6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="961f6-108">Return Value</span></span>  
 <span data-ttu-id="961f6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="961f6-109">S_OK</span></span>  
 <span data-ttu-id="961f6-110">시작 알림 이벤트에 대한 핸들을 성공적으로 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="961f6-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="961f6-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="961f6-112">`phStartupEvent`가 null이거나 `debuggeePID`가 현재 실행 중인 프로세스를 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="961f6-113">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="961f6-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="961f6-114">시작 알림 이벤트에 대한 핸들을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="961f6-115">설명</span><span class="sxs-lookup"><span data-stu-id="961f6-115">Remarks</span></span>  
 <span data-ttu-id="961f6-116">Windows 운영 체제에서 `debuggeePID`는 OS 프로세스 식별자에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="961f6-117">이벤트 신호를 전송한 CLR에서 관리 코드를 실행하기 전에 이벤트 신호가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="961f6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="961f6-118">Requirements</span></span>  
 <span data-ttu-id="961f6-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="961f6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961f6-120">**헤더:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="961f6-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="961f6-121">**라이브러리:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="961f6-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="961f6-122">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="961f6-122">**.NET Framework Versions:** 3.5 SP1</span></span>
