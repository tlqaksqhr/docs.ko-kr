---
title: "ICorDebugModule::GetProcess 메서드"
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
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bdb1337b6aebdb34b76adbbd2fd54d019b5b2abf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="1a9a6-102">ICorDebugModule::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="1a9a6-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="1a9a6-103">이 모듈의 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a9a6-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a9a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a9a6-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a9a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a9a6-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="1a9a6-106">[out] 이 모듈을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1a9a6-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a9a6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a9a6-107">Requirements</span></span>  
 <span data-ttu-id="1a9a6-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a9a6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a9a6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a9a6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a9a6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a9a6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a9a6-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a9a6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
