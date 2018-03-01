---
title: "ICorDebugFunction::GetClass 메서드"
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
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4607b5c71311eeccc9df778a45ca30a305b90aa9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="e1b68-102">ICorDebugFunction::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="e1b68-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="e1b68-103">이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b68-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1b68-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1b68-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1b68-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="e1b68-106">[out] 주소에 대 한 포인터는 `ICorDebugClass` 이 함수가 클래스의 멤버인 경우 클래스 또는 null을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1b68-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1b68-107">Requirements</span></span>  
 <span data-ttu-id="e1b68-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b68-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1b68-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1b68-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1b68-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1b68-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1b68-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1b68-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
