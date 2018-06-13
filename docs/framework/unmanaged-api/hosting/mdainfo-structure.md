---
title: MDAInfo 구조체
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5164e85ecc97de99dcc493c2ba5efa8fc3468471
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443182"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="0eb44-102">MDAInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="0eb44-102">MDAInfo Structure</span></span>
<span data-ttu-id="0eb44-103">에 대 한 세부 정보를 제공는 `Event_MDAFired` 관리 디버깅 도우미 (MDA) 만들기를 트리거하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb44-104">구문</span><span class="sxs-lookup"><span data-stu-id="0eb44-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="0eb44-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0eb44-105">Members</span></span>  
  
|<span data-ttu-id="0eb44-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0eb44-106">Member</span></span>|<span data-ttu-id="0eb44-107">설명</span><span class="sxs-lookup"><span data-stu-id="0eb44-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="0eb44-108">현재 MDA의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-108">The title of the current MDA.</span></span> <span data-ttu-id="0eb44-109">오류를 발생 시킨의 종류를 설명 하는 제목은 `Event_MDAFired` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="0eb44-110">현재 MDA에서 제공 되는 출력 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eb44-111">설명</span><span class="sxs-lookup"><span data-stu-id="0eb44-111">Remarks</span></span>  
 <span data-ttu-id="0eb44-112">관리 디버깅 도우미 (Mda)은 런타임 실행 엔진에서 디버깅 하는 공용 언어 런타임 (CLR)를 식별 하는 등의 작업 수행과 함께에서 작동 하는 도우미 또는 상태에 대 한 추가 정보를 덤프는 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="0eb44-113">Mda는 트래핑할 수 없는 이벤트에 대 한 XML 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="0eb44-114">관리 코드와 비관리 코드 간의 전환 디버깅에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="0eb44-115">런타임에는 MDA 만들기를 트리거하는 이벤트가 발생 하면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="0eb44-116">호스트 등록 하지 않은 경우는 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 호출 하 여 인스턴스 [iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 알려야 하는 `Event_MDAFired` 으로 이벤트를 런타임 진행 해당 기본값, 호스팅되지 않은 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="0eb44-117">이 이벤트에 대 한 처리기를 등록 하는 호스트 하는 경우 런타임에서 프로세스에 디버거가 연결 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="0eb44-118">인 경우 런타임은 디버거에서 실행을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="0eb44-119">디버거에서 계속 될 때 호스트를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="0eb44-120">디버거가 연결 되 면 런타임에서 호출 `IActionOnCLREvent::OnEvent` 전달에 대 한 포인터는 `MDAInfo` 인스턴스로 `data` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="0eb44-121">Mda를 활성화 하 고 MDA가 활성화 될 때 알림을 받을 수는 호스트 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="0eb44-122">이 기회 호스트는 기본 동작을 재정의 하 고 프로세스 상태가 손상 되지 않도록 하려면 이벤트를 발생 하는 관리 되는 스레드를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="0eb44-123">Mda를 사용 하는 방법에 대 한 자세한 내용은 참조 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb44-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0eb44-124">Requirements</span></span>  
 <span data-ttu-id="0eb44-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb44-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eb44-126">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="0eb44-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0eb44-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0eb44-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0eb44-128">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eb44-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb44-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0eb44-129">See Also</span></span>  
 [<span data-ttu-id="0eb44-130">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="0eb44-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="0eb44-131">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="0eb44-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
