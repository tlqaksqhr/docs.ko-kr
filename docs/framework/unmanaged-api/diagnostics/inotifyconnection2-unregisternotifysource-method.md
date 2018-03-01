---
title: "INotifyConnection2::UnregisterNotifySource 메서드"
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
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 308055a0b8a5d07d93838479de6c1dae3c29517d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="38342-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="38342-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="38342-103">연결에서 지정 된 알림 원본 개체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="38342-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38342-104">구문</span><span class="sxs-lookup"><span data-stu-id="38342-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38342-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38342-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="38342-106">[in] 등록을 취소할 알림 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38342-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38342-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="38342-107">Return Value</span></span>  
 <span data-ttu-id="38342-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="38342-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38342-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38342-109">Requirements</span></span>  
 <span data-ttu-id="38342-110">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="38342-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38342-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38342-111">See Also</span></span>  
 [<span data-ttu-id="38342-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38342-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="38342-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38342-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="38342-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38342-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="38342-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="38342-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
