---
title: ICorDebugILFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd421d705a96778159cb80ad92d9ac654e88985f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414068"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="0accc-102">ICorDebugILFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="0accc-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="0accc-103">명령 포인터의 값 및 명령 포인터의 값을 가져온 방법에 대해 설명 하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0accc-104">구문</span><span class="sxs-lookup"><span data-stu-id="0accc-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0accc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0accc-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="0accc-106">[out] 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="0accc-107">[out] 명령 포인터의 값을 가져온 방법에 대해 설명 하는 CorDebugMappingResult 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0accc-108">설명</span><span class="sxs-lookup"><span data-stu-id="0accc-108">Remarks</span></span>  
 <span data-ttu-id="0accc-109">명령 포인터의 값은 함수의 Microsoft MSIL (intermediate language) 코드에 대 한 스택 프레임의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="0accc-110">스택 프레임 활성 상태 이면이 주소는 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="0accc-111">스택 프레임 활성 상태 이면이 주소는 스택 프레임을 다시 활성화 될 때 실행 하려면 다음 명령을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="0accc-112">이 프레임은 적시에 (JIT) 컴파일된 프레임을 역방향으로 매핑하여 실제 네이티브 명령 포인터의 값을 근사치만 않을 명령 포인터의 값이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0accc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0accc-113">Requirements</span></span>  
 <span data-ttu-id="0accc-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0accc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0accc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0accc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0accc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0accc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0accc-117">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0accc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
