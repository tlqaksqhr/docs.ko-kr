---
title: "ICorDebugAppDomain::Attach 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.Attach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25f6d32cc1b06615c592739ffab8a87f0fe5d5b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="d051b-102">ICorDebugAppDomain::Attach 메서드</span><span class="sxs-lookup"><span data-stu-id="d051b-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="d051b-103">응용 프로그램 도메인에서 디버거를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="d051b-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d051b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d051b-104">Syntax</span></span>  
  
```  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d051b-105">설명</span><span class="sxs-lookup"><span data-stu-id="d051b-105">Remarks</span></span>  
 <span data-ttu-id="d051b-106">이벤트를 수신 하 고 응용 프로그램 도메인의 디버깅을 사용 하려면 응용 프로그램 도메인에서 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d051b-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d051b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d051b-107">Requirements</span></span>  
 <span data-ttu-id="d051b-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d051b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d051b-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d051b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d051b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d051b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d051b-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d051b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
