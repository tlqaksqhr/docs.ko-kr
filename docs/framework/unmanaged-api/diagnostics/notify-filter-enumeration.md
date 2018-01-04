---
title: "NOTIFY_FILTER 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NOTIFY_FILTER
api_location: diasymreader.dll
api_type: COM
f1_keywords: NOTIFY_FILTER
helpviewer_keywords: NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef72cb965bec8f424f5df35d4f66715fa11a5e46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="cc3b6-102">NOTIFY_FILTER 열거형</span><span class="sxs-lookup"><span data-stu-id="cc3b6-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="cc3b6-103">디버거 기능에 대 한 콜백을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="cc3b6-104">자세한 내용은 참조는 [inotifysource2:: Setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3b6-105">구문</span><span class="sxs-lookup"><span data-stu-id="cc3b6-105">Syntax</span></span>  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="cc3b6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cc3b6-106">Members</span></span>  
  
|<span data-ttu-id="cc3b6-107">멤버</span><span class="sxs-lookup"><span data-stu-id="cc3b6-107">Member</span></span>|<span data-ttu-id="cc3b6-108">설명</span><span class="sxs-lookup"><span data-stu-id="cc3b6-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="cc3b6-109">나타냅니다는 [inotifysink2:: Onsynccallout](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="cc3b6-110">나타냅니다는 [inotifysink2:: Onsynccallenter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="cc3b6-111">나타냅니다는 [inotifysink2:: Onsynccallexit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="cc3b6-112">나타냅니다는 [inotifysink2:: Onsynccallreturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="cc3b6-113">나타내는 모든는 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="cc3b6-114">모든 기존 및 차후의 알림을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="cc3b6-115">없는 알림 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc3b6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc3b6-116">Requirements</span></span>  
 <span data-ttu-id="cc3b6-117">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="cc3b6-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3b6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc3b6-118">See Also</span></span>  
 [<span data-ttu-id="cc3b6-119">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="cc3b6-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
