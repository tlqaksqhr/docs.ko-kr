---
title: "ICorDebugInternalFrame::GetFrameType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame.GetFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 476903ae8f1461a46d685bc3e549c3b6553d5c68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="25c86-102">ICorDebugInternalFrame::GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="25c86-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="25c86-103">이 내부 프레임의 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25c86-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25c86-104">구문</span><span class="sxs-lookup"><span data-stu-id="25c86-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25c86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25c86-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="25c86-106">[out] 이 표시 되는 내부 프레임의 유형을 나타내는 CorDebugInternalFrameType 열거형의 값에 대 한 포인터 `ICorDebugInternalFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="25c86-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25c86-107">설명</span><span class="sxs-lookup"><span data-stu-id="25c86-107">Remarks</span></span>  
 <span data-ttu-id="25c86-108">내부 프레임 유형 STUBFRAME_NONE 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c86-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="25c86-109">디버거에서는 인식할 수 없는 내부 프레임 형식을 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c86-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25c86-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25c86-110">Requirements</span></span>  
 <span data-ttu-id="25c86-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25c86-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25c86-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25c86-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25c86-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25c86-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25c86-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25c86-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
