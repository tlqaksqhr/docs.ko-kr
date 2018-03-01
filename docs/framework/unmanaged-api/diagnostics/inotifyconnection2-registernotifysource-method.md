---
title: "INotifyConnection2::RegisterNotifySource 메서드"
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
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a141872dc5699e5b317b21f03672fe0d76096392
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="dea92-102">INotifyConnection2::RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="dea92-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="dea92-103">지정 된 알림 소스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dea92-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea92-104">구문</span><span class="sxs-lookup"><span data-stu-id="dea92-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dea92-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dea92-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="dea92-106">[in] 알림 원본으로 사용할 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea92-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="dea92-107">[out] 알림 싱크로 사용할 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dea92-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dea92-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="dea92-108">Return Value</span></span>  
 <span data-ttu-id="dea92-109">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="dea92-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea92-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dea92-110">Requirements</span></span>  
 <span data-ttu-id="dea92-111">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="dea92-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea92-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dea92-112">See Also</span></span>  
 [<span data-ttu-id="dea92-113">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dea92-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="dea92-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dea92-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="dea92-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dea92-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="dea92-116">UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="dea92-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
