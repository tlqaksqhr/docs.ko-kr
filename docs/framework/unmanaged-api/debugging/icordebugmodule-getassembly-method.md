---
title: ICorDebugModule::GetAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78bfc91bdd0f9fa68252c6a07e1362807eb507b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416025"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="218ba-102">ICorDebugModule::GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="218ba-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="218ba-103">이 모듈에 대 한 포함 하는 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="218ba-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="218ba-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="218ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="218ba-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="218ba-106">[out] 이 모듈을 포함 하는 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="218ba-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218ba-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="218ba-107">Requirements</span></span>  
 <span data-ttu-id="218ba-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="218ba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218ba-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="218ba-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="218ba-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="218ba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="218ba-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218ba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
