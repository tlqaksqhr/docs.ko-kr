---
title: "ICorDebugProcess::GetID 메서드"
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
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d09888434048c312bd78dddf29d39a45f023695e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="97ada-102">ICorDebugProcess::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="97ada-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="97ada-103">프로세스의 운영 체제 (OS) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97ada-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ada-104">구문</span><span class="sxs-lookup"><span data-stu-id="97ada-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97ada-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97ada-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="97ada-106">[out] 프로세스의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="97ada-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ada-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97ada-107">Requirements</span></span>  
 <span data-ttu-id="97ada-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97ada-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ada-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97ada-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97ada-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97ada-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97ada-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ada-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
