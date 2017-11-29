---
title: "ICorPublishEnum::Clone 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum.Clone
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 607d89f2220f18d58b03b4fdc8a3819e29cdc60d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="1f52b-102">ICorPublishEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="1f52b-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="1f52b-103">이 파일의 복사본을 만듭니다 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f52b-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f52b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f52b-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f52b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f52b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1f52b-106">[out] 주소에 대 한 포인터는 `ICorPublishEnum` 개체를이 파일의 복사본 `ICorPublishEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f52b-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f52b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f52b-107">Requirements</span></span>  
 <span data-ttu-id="1f52b-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f52b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f52b-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1f52b-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1f52b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f52b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f52b-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f52b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f52b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f52b-112">See Also</span></span>  
 [<span data-ttu-id="1f52b-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f52b-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
