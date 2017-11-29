---
title: "ICorDebugStepper::Deactivate 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Deactivate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 056d60a56c37126163361166e16da5d7949e2dbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="d36a8-102">ICorDebugStepper::Deactivate 메서드</span><span class="sxs-lookup"><span data-stu-id="d36a8-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="d36a8-103">이 ICorDebugStepper 받은 마지막 단계 명령 취소 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d36a8-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="d36a8-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d36a8-105">설명</span><span class="sxs-lookup"><span data-stu-id="d36a8-105">Remarks</span></span>  
 <span data-ttu-id="d36a8-106">가장 최근에 수신한 단계 명령이 취소 된 후에 새 단계별 실행 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36a8-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36a8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d36a8-107">Requirements</span></span>  
 <span data-ttu-id="d36a8-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d36a8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36a8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d36a8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d36a8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d36a8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d36a8-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
