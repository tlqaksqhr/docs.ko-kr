---
title: "INotifySink2::OnSyncCallOut 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2.OnSyncCallOut
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 427b54a66b92ef23572739d6c9e0dfd5731eb638
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="07fa5-102">INotifySink2::OnSyncCallOut 메서드</span><span class="sxs-lookup"><span data-stu-id="07fa5-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="07fa5-103">되 면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fa5-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fa5-104">구문</span><span class="sxs-lookup"><span data-stu-id="07fa5-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07fa5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07fa5-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="07fa5-106">[in] 이 호출의 ID입니다. 참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07fa5-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="07fa5-107">[out] 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fa5-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="07fa5-108">[out] 호출 버퍼의 바이트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="07fa5-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07fa5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="07fa5-109">Return Value</span></span>  
 <span data-ttu-id="07fa5-110">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="07fa5-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07fa5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07fa5-111">Requirements</span></span>  
 <span data-ttu-id="07fa5-112">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="07fa5-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fa5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07fa5-113">See Also</span></span>  
 [<span data-ttu-id="07fa5-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07fa5-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="07fa5-115">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07fa5-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="07fa5-116">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07fa5-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
