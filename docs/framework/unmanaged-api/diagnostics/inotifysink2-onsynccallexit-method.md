---
title: INotifySink2::OnSyncCallExit 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fe2ebecdacd3b848d5de7eecca4753a89a58f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432481"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="f5508-102">INotifySink2::OnSyncCallExit 메서드</span><span class="sxs-lookup"><span data-stu-id="f5508-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="f5508-103">호출을 종료할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5508-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5508-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5508-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5508-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="f5508-106">[in] 종료 된 호출의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="f5508-107">참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="f5508-108">[out] 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="f5508-109">[out] 호출 버퍼의 바이트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5508-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="f5508-110">Return Value</span></span>  
 <span data-ttu-id="f5508-111">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5508-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5508-112">Requirements</span></span>  
 <span data-ttu-id="f5508-113">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="f5508-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5508-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5508-114">See Also</span></span>  
 [<span data-ttu-id="f5508-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5508-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="f5508-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5508-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="f5508-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5508-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
