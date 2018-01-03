---
title: "ICorDebugAssembly::GetProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbb62bb6d2731c5bc2618de0a71f75e0979808c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="41488-102">ICorDebugAssembly::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="41488-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="41488-103">이 ICorDebugAssembly 인스턴스가 실행 중인 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41488-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41488-104">구문</span><span class="sxs-lookup"><span data-stu-id="41488-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41488-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41488-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="41488-106">[out] 프로세스를 나타내는 ICorDebugProcess 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="41488-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41488-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41488-107">Requirements</span></span>  
 <span data-ttu-id="41488-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41488-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41488-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41488-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41488-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41488-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41488-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41488-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
