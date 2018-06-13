---
title: ICorDebugFrame::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b622d1bd82e53d5fa232e07b1f49e6fbba3ccba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414845"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="6de93-102">ICorDebugFrame::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="6de93-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="6de93-103">이 스택 프레임과 연결 된 코드를 포함 하는 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6de93-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de93-104">구문</span><span class="sxs-lookup"><span data-stu-id="6de93-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6de93-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6de93-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="6de93-106">[out] 이 스택 프레임과 연결 된 코드를 포함 하는 기능을 나타내는 ICorDebugFunction 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6de93-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6de93-107">설명</span><span class="sxs-lookup"><span data-stu-id="6de93-107">Remarks</span></span>  
 <span data-ttu-id="6de93-108">`GetFunction` 프레임 특정 함수에 연결 되지 않은 경우 메서드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6de93-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de93-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6de93-109">Requirements</span></span>  
 <span data-ttu-id="6de93-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6de93-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de93-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de93-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de93-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de93-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6de93-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de93-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
