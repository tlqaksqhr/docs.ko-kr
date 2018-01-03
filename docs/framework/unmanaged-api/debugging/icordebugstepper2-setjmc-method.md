---
title: "ICorDebugStepper2::SetJMC 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper2.SetJMC
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fbbe0d3e42df073a5718ca037b44f6f2f31ec23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="33026-102">ICorDebugStepper2::SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="33026-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="33026-103">응용 프로그램 개발자가 작성 하는 코드를 사용할 때만이 ICorDebugStepper 단계 있는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33026-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="33026-104">이 프로세스와 내 코드만 (JMC) 디버깅 말합니다.</span><span class="sxs-lookup"><span data-stu-id="33026-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33026-105">구문</span><span class="sxs-lookup"><span data-stu-id="33026-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33026-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33026-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="33026-107">[in] 로 설정 `true` 응용 프로그램 개발자가 작성 합니다; 그렇지 않으면로 설정 되는 코드를 사용할 때만 단계로 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="33026-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33026-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33026-108">Requirements</span></span>  
 <span data-ttu-id="33026-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33026-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33026-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33026-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33026-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33026-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33026-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33026-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
