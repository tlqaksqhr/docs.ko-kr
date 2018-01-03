---
title: "ICorDebug::Initialize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Initialize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dff8e5472879bfffb0489f113e9d88527569fa1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="ee3df-102">ICorDebug::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="ee3df-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="ee3df-103">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee3df-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee3df-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee3df-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ee3df-105">설명</span><span class="sxs-lookup"><span data-stu-id="ee3df-105">Remarks</span></span>  
 <span data-ttu-id="ee3df-106">디버거를 호출 해야 `Initialize` 디버깅 초기화에 시간이 서비스를 만들 때.</span><span class="sxs-lookup"><span data-stu-id="ee3df-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="ee3df-107">이 메서드를 다른 메서드 전에 호출 해야 `ICorDebug` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee3df-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee3df-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee3df-108">Requirements</span></span>  
 <span data-ttu-id="ee3df-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3df-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee3df-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee3df-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee3df-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee3df-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee3df-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee3df-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3df-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee3df-113">See Also</span></span>  
 [<span data-ttu-id="ee3df-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee3df-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
