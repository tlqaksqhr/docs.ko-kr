---
title: "ICorDebugVariableHome::GetCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fccbd05ac03aca640e3f847abaa68ca84949110
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="623d5-102">ICorDebugVariableHome::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="623d5-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="623d5-103">이 포함 하는 "ICorDebugCode" 인스턴스로 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="623d5-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="623d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="623d5-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="623d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="623d5-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="623d5-106">[out] 이 포함 하는 "ICorDebugCode" 인스턴스 주소에 대 한 포인터 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="623d5-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="623d5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="623d5-107">Requirements</span></span>  
 <span data-ttu-id="623d5-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="623d5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="623d5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="623d5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="623d5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="623d5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="623d5-111">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="623d5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="623d5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="623d5-112">See Also</span></span>  
 [<span data-ttu-id="623d5-113">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="623d5-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 
