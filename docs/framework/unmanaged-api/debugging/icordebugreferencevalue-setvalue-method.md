---
title: "ICorDebugReferenceValue::SetValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.SetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 764b99b5687c171b0dcdbc7f8ca15493c182ff7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="42deb-102">ICorDebugReferenceValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="42deb-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="42deb-103">지정된 된 메모리 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="42deb-103">Sets the specified memory address.</span></span> <span data-ttu-id="42deb-104">즉,이 메서드는이 ICorDebugReferenceValue 개체를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42deb-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42deb-105">구문</span><span class="sxs-lookup"><span data-stu-id="42deb-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42deb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42deb-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="42deb-107">[in] A `CORDB_ADDRESS` 이 개체의 주소를 지정 하는 값 `ICorDebugReferenceValue` 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="42deb-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42deb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42deb-108">Requirements</span></span>  
 <span data-ttu-id="42deb-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42deb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42deb-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42deb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42deb-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42deb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42deb-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42deb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
