---
title: "ICorDebugEnum::Clone 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.Clone
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ddd7d82b6eb2944b1d2a5d7a83f0ccc9f255e45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="b6604-102">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="b6604-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="b6604-103">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6604-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6604-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6604-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6604-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6604-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b6604-106">[out] 주소에 대 한 포인터는 `ICorDebugEnum` 개체를이 파일의 복사본 `ICorDebugEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b6604-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6604-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6604-107">Requirements</span></span>  
 <span data-ttu-id="b6604-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6604-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6604-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6604-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6604-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6604-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6604-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6604-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
