---
title: "ICorDebugNativeFrame::GetIP 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ceb0188ce2a52c3950b5fc89ea15c96852910d88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="7b1c1-102">ICorDebugNativeFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1c1-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="7b1c1-103">가져옵니다 네이티브 코드 오프셋의 명령 포인터 현재 설정 된 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1c1-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b1c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b1c1-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b1c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b1c1-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="7b1c1-106">[out] 네이티브 코드 내의 오프셋된 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1c1-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b1c1-107">설명</span><span class="sxs-lookup"><span data-stu-id="7b1c1-107">Remarks</span></span>  
 <span data-ttu-id="7b1c1-108">이 "ICorDebugNativeFrame"으로 표시 되는 스택 프레임 활성 상태 이면 오프셋 다음에 실행할 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1c1-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="7b1c1-109">이 스택 프레임 활성 상태 이면 오프셋 스택 프레임을 다시 활성화 될 때 실행 되는 다음 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b1c1-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b1c1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b1c1-110">Requirements</span></span>  
 <span data-ttu-id="7b1c1-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b1c1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b1c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b1c1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b1c1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b1c1-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b1c1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1c1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b1c1-115">See Also</span></span>  
 
