---
title: "ICorDebugArrayValue::GetElement 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetElement
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9aba987aa6f806bfe1608e081aac4cb501cd23fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="4187b-102">ICorDebugArrayValue::GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="4187b-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="4187b-103">지정 된 배열 요소 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4187b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4187b-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4187b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4187b-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="4187b-106">[in] 이 차원 수가 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="4187b-107">또한이 값은의 크기는 `indices` 배열 크기의 차원 수와 같은지는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="4187b-108">[in] 각각의 차원 내의 위치를 지정 하는 인덱스 값의 배열에서 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="4187b-109">이 값은 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4187b-110">[out] 지정 된 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4187b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4187b-111">Requirements</span></span>  
 <span data-ttu-id="4187b-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4187b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4187b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4187b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4187b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4187b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4187b-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4187b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
