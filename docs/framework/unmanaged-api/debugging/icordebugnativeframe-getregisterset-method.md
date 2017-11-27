---
title: "ICorDebugNativeFrame::GetRegisterSet 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7689632d41971d85417501e9a7f90712a07b34bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="465c7-102">ICorDebugNativeFrame::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="465c7-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="465c7-103">이 스택 프레임에 대해 설정 하는 레지스터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="465c7-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="465c7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="465c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="465c7-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="465c7-106">[out] 주소에 대 한 포인터는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 스택 프레임에 대해 설정 하는 레지스터를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="465c7-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="465c7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="465c7-107">Requirements</span></span>  
 <span data-ttu-id="465c7-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="465c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="465c7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="465c7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="465c7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="465c7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="465c7-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="465c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465c7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="465c7-112">See Also</span></span>  
 
