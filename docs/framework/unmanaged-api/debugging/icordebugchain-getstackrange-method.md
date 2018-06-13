---
title: ICorDebugChain::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402472"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="e1aea-102">ICorDebugChain::GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="e1aea-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="e1aea-103">이 체인에 대 한 스택 세그먼트의 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1aea-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1aea-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1aea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1aea-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="e1aea-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 값 스택 세그먼트의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="e1aea-107">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 값 스택 세그먼트의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1aea-108">설명</span><span class="sxs-lookup"><span data-stu-id="e1aea-108">Remarks</span></span>  
 <span data-ttu-id="e1aea-109">숫자 범위가 스택 프레임 위치를 비교 하기 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="e1aea-110">스택에 실제로 저장 된 항목에 대 한 가정을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1aea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1aea-111">Requirements</span></span>  
 <span data-ttu-id="e1aea-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1aea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1aea-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1aea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1aea-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1aea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1aea-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1aea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
