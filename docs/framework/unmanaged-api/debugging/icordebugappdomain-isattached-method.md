---
title: "ICorDebugAppDomain::IsAttached 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.IsAttached
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85b674ad705f77e00cf2a8a5286d6a74f7a646
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="df7a6-102">ICorDebugAppDomain::IsAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="df7a6-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="df7a6-103">응용 프로그램 도메인에서 디버거가 연결 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df7a6-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="df7a6-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df7a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df7a6-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="df7a6-106">[out] `true` 디버거 고, 그렇지 않으면 응용 프로그램 도메인에 연결 된 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="df7a6-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df7a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="df7a6-107">Remarks</span></span>  
 <span data-ttu-id="df7a6-108">응용 프로그램 도메인에서 디버거가 연결 될 때까지 ICorDebugController 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df7a6-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7a6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df7a6-109">Requirements</span></span>  
 <span data-ttu-id="df7a6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7a6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df7a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df7a6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df7a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df7a6-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
