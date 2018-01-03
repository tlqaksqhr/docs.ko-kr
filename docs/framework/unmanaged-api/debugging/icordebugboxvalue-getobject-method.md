---
title: "ICorDebugBoxValue::GetObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBoxValue.GetObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e71da40af57d00e4651c094ddad9c86fc6fe636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="cdba7-102">ICorDebugBoxValue::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="cdba7-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="cdba7-103">Boxed 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdba7-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdba7-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdba7-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdba7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdba7-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="cdba7-106">[out] Boxed 값을 나타내는 ICorDebugObjectValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdba7-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdba7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdba7-107">Requirements</span></span>  
 <span data-ttu-id="cdba7-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdba7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdba7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdba7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdba7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdba7-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdba7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
