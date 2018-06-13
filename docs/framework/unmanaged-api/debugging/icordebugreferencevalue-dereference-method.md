---
title: ICorDebugReferenceValue::Dereference 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a0fd1981e7da5af19cf3a422c6008d373e9ac92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416595"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="bc802-102">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="bc802-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="bc802-103">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc802-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc802-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc802-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc802-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc802-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="bc802-106">[out] 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc802-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc802-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc802-107">Remarks</span></span>  
 <span data-ttu-id="bc802-108">`ICorDebugValue` 개체는 해당 참조가 아직 비활성화 되지 않은 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc802-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc802-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc802-109">Requirements</span></span>  
 <span data-ttu-id="bc802-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc802-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc802-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc802-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc802-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc802-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc802-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc802-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
