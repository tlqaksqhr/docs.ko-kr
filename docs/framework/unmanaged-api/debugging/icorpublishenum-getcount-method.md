---
title: "ICorPublishEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum.GetCount
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7b91c11482a1314bc86b464715dcba68f2a67724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="c7c0c-102">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c7c0c-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="c7c0c-103">열거형에서 항목의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7c0c-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c0c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7c0c-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7c0c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7c0c-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c7c0c-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7c0c-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7c0c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7c0c-107">Requirements</span></span>  
 <span data-ttu-id="c7c0c-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c0c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7c0c-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c7c0c-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c7c0c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7c0c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7c0c-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c0c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c0c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7c0c-112">See Also</span></span>  
 [<span data-ttu-id="c7c0c-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7c0c-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
