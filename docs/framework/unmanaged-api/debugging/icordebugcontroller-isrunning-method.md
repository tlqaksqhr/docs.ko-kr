---
title: "ICorDebugController::IsRunning 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.IsRunning
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0cfb2c0fe3c2ebf9473afc4f1a93f50e8fe437f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="aa382-102">ICorDebugController::IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="aa382-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="aa382-103">프로세스의 스레드는 현재 실행에 자유롭게 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa382-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa382-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa382-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa382-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa382-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="aa382-106">[out] 값에 대 한 포인터 `true` 자유롭게, 그렇지 않으면 프로세스의 스레드가 실행 중인 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa382-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa382-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa382-107">Requirements</span></span>  
 <span data-ttu-id="aa382-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa382-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa382-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa382-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa382-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa382-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa382-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa382-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa382-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa382-112">See Also</span></span>  
 
