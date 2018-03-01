---
title: "ICorDebugStepper::SetUnmappedStopMask 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fffd523caef6bba1b495f9b8a257f57bd8955af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="2bdf1-102">ICorDebugStepper::SetUnmappedStopMask 메서드</span><span class="sxs-lookup"><span data-stu-id="2bdf1-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="2bdf1-103">매핑되지 않은 코드 실행을 중지할의 유형을 지정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bdf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2bdf1-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bdf1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bdf1-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="2bdf1-106">[in] 디버거는 실행을 중단 하는 데는 비관리 코드의 형식을 지정 하는 CorDebugUnmappedStop 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="2bdf1-107">기본값은 STOP_OTHER_UNMAPPED 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="2bdf1-108">값 STOP_UNMANAGED interop 디버깅에 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bdf1-109">설명</span><span class="sxs-lookup"><span data-stu-id="2bdf1-109">Remarks</span></span>  
 <span data-ttu-id="2bdf1-110">디버거는 적시에 (JIT) 컴파일에 Microsoft MSIL (intermediate language)로 해당 매핑되지는를 찾으면; 비관리 코드의 해당 형식을 지정 하는 플래그 설정 된 경우 실행 중단 그렇지 않은 경우 단계별 실행 투명 하 게 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="2bdf1-111">디버거를 사용 하지 않는 스텝 메서드를 입력 하는 경우 다음 않습니다 반드시 실행 되지 매핑되지 않은 코드.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bdf1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bdf1-112">Requirements</span></span>  
 <span data-ttu-id="2bdf1-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2bdf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bdf1-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bdf1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bdf1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bdf1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bdf1-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bdf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
