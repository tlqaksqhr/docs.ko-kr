---
title: "ICorDebugReferenceValue::Dereference 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.Dereference
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0dbf2775217a78c1cbb9a96093354f0fc0b278bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="42428-102">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="42428-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="42428-103">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="42428-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42428-104">구문</span><span class="sxs-lookup"><span data-stu-id="42428-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42428-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42428-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="42428-106">[out] 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42428-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42428-107">설명</span><span class="sxs-lookup"><span data-stu-id="42428-107">Remarks</span></span>  
 <span data-ttu-id="42428-108">`ICorDebugValue` 개체는 해당 참조가 아직 비활성화 되지 않은 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="42428-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42428-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42428-109">Requirements</span></span>  
 <span data-ttu-id="42428-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42428-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42428-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42428-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42428-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42428-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42428-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42428-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
