---
title: ICorDebugStepper2::SetJMC 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ad05d2f6226d570fc854fb48575851dd718e410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418199"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="83984-102">ICorDebugStepper2::SetJMC 메서드</span><span class="sxs-lookup"><span data-stu-id="83984-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="83984-103">응용 프로그램 개발자가 작성 하는 코드를 사용할 때만이 ICorDebugStepper 단계 있는지 여부를 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83984-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="83984-104">이 프로세스와 내 코드만 (JMC) 디버깅 말합니다.</span><span class="sxs-lookup"><span data-stu-id="83984-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83984-105">구문</span><span class="sxs-lookup"><span data-stu-id="83984-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83984-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83984-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="83984-107">[in] 로 설정 `true` 응용 프로그램 개발자가 작성 합니다; 그렇지 않으면로 설정 되는 코드를 사용할 때만 단계로 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="83984-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83984-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83984-108">Requirements</span></span>  
 <span data-ttu-id="83984-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83984-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83984-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83984-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83984-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83984-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83984-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83984-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
