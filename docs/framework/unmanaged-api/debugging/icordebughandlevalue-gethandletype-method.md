---
title: "ICorDebugHandleValue::GetHandleType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue.GetHandleType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b41e7c14fd0abdd957f0661345a6372074f2ed7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="19724-102">ICorDebugHandleValue::GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="19724-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="19724-103">이 ICorDebugHandleValue 개체에서 참조 하는 핸들의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19724-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19724-104">구문</span><span class="sxs-lookup"><span data-stu-id="19724-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19724-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19724-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="19724-106">[out] 이 핸들의 형식을 나타내는 CorDebugHandleType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19724-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19724-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19724-107">Requirements</span></span>  
 <span data-ttu-id="19724-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19724-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19724-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19724-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19724-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19724-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19724-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19724-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
