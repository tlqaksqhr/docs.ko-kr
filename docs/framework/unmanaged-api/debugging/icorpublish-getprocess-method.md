---
title: ICorPublish::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 414bc1bbd3578d0707e35fa70fe196b504af9942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418498"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="9de71-102">ICorPublish::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="9de71-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="9de71-103">가져옵니다는 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 지정한 식별자를 가진 프로세스를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9de71-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de71-104">구문</span><span class="sxs-lookup"><span data-stu-id="9de71-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9de71-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9de71-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="9de71-106">[in] 프로세스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9de71-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9de71-107">[out] 주소에 대 한 포인터는 `ICorPublishProcess` 프로세스를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9de71-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de71-108">설명</span><span class="sxs-lookup"><span data-stu-id="9de71-108">Remarks</span></span>  
 <span data-ttu-id="9de71-109">`GetProcess` 프로세스가 존재 하지 않거나 현재 사용자가 디버깅할 수 있는 관리 되는 프로세스가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de71-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de71-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9de71-110">Requirements</span></span>  
 <span data-ttu-id="9de71-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9de71-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9de71-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="9de71-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9de71-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9de71-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9de71-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9de71-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de71-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9de71-115">See Also</span></span>  
 [<span data-ttu-id="9de71-116">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de71-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
