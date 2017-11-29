---
title: "ICorDebugFrame::GetCallee 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54a26ad7d4818aae81b765ab4e6c0e5be821680e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="ae3aa-102">ICorDebugFrame::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="ae3aa-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="ae3aa-103">이 프레임을 호출한 현재 체인에서 ICorDebugFrame 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae3aa-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae3aa-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae3aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae3aa-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="ae3aa-106">[out] 주소에 대 한 포인터는 `ICorDebugFrame` 호출된 프레임을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3aa-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="ae3aa-107">이 값은 호출 프레임은 현재 체인에서 가장 안쪽 프레임 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3aa-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae3aa-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae3aa-108">Requirements</span></span>  
 <span data-ttu-id="ae3aa-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3aa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3aa-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae3aa-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae3aa-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae3aa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae3aa-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3aa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
