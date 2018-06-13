---
title: ICorDebugAssembly::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1c3bcc0ed22fa970d92e2384277d0786016db19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402111"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="6de14-102">ICorDebugAssembly::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="6de14-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="6de14-103">이 ICorDebugAssembly 인스턴스가 실행 중인 프로세스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6de14-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de14-104">구문</span><span class="sxs-lookup"><span data-stu-id="6de14-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6de14-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6de14-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="6de14-106">[out] 프로세스를 나타내는 ICorDebugProcess 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6de14-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de14-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6de14-107">Requirements</span></span>  
 <span data-ttu-id="6de14-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6de14-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de14-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de14-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de14-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de14-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6de14-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de14-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
