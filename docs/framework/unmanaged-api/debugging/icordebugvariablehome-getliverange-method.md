---
title: "IcorDebugVariableHome::GetLiveRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetLiveRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8554bf2667f3542b3164b60eaed998087fe175d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="27e38-102">IcorDebugVariableHome::GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="27e38-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="27e38-103">이 변수는 라이브 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27e38-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e38-104">구문</span><span class="sxs-lookup"><span data-stu-id="27e38-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27e38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27e38-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="27e38-106">[out] 변수는 첫 번째 실시간 논리 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="27e38-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="27e38-107">[out] 변수는 마지막 실시간 포인터 바로 뒤의 논리 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="27e38-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27e38-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27e38-108">Requirements</span></span>  
 <span data-ttu-id="27e38-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e38-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e38-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27e38-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27e38-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27e38-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27e38-112">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e38-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e38-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27e38-113">See Also</span></span>  
 [<span data-ttu-id="27e38-114">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e38-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
