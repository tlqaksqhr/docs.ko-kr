---
title: ICorDebugEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da16a22c71c1fac1932f74a9af18fbc30eb326f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410834"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="14140-102">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="14140-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="14140-103">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14140-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14140-104">구문</span><span class="sxs-lookup"><span data-stu-id="14140-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14140-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14140-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="14140-106">[out] 주소에 대 한 포인터는 `ICorDebugEnum` 개체를이 파일의 복사본 `ICorDebugEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="14140-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14140-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14140-107">Requirements</span></span>  
 <span data-ttu-id="14140-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14140-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14140-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14140-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14140-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14140-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14140-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14140-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
