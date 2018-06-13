---
title: ICorPublishEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d9e468027e88cc74900364459f83d7e5125a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423808"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="60145-102">ICorPublishEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="60145-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="60145-103">이 파일의 복사본을 만듭니다 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="60145-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60145-104">구문</span><span class="sxs-lookup"><span data-stu-id="60145-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60145-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60145-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="60145-106">[out] 주소에 대 한 포인터는 `ICorPublishEnum` 개체를이 파일의 복사본 `ICorPublishEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="60145-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60145-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60145-107">Requirements</span></span>  
 <span data-ttu-id="60145-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60145-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60145-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="60145-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="60145-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60145-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60145-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60145-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60145-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60145-112">See Also</span></span>  
 [<span data-ttu-id="60145-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60145-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
