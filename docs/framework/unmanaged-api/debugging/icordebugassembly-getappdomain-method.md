---
title: "ICorDebugAssembly::GetAppDomain 메서드"
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
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f97795568b9811d0dbf7852fd64d5256c29b8f30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="59676-102">ICorDebugAssembly::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="59676-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="59676-103">이 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="59676-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59676-104">구문</span><span class="sxs-lookup"><span data-stu-id="59676-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59676-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59676-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="59676-106">[out] 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59676-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59676-107">설명</span><span class="sxs-lookup"><span data-stu-id="59676-107">Remarks</span></span>  
 <span data-ttu-id="59676-108">이 어셈블리는 시스템 어셈블리 경우 `GetAppDomain` null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59676-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59676-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59676-109">Requirements</span></span>  
 <span data-ttu-id="59676-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59676-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59676-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59676-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59676-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59676-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59676-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
