---
title: "ICorDebugAppDomain2::GetFunctionPointerType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetFunctionPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85c07ec6177621b571a376ad58a386e8ed31ea63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="e6498-102">ICorDebugAppDomain2::GetFunctionPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="e6498-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="e6498-103">지정 된 시그니처가 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6498-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6498-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6498-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e6498-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="e6498-106">[in] 함수에 대 한 형식 인수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="e6498-107">[in] 포인터의 배열을, 각각 함수의 형식 인수를 나타내는 ICorDebugType 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="e6498-108">첫 번째 요소는 반환 형식입니다. 각각의 다른 요소에는 매개 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="e6498-109">[out] 주소에 대 한 포인터는 `ICorDebugType` 함수에 포인터를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6498-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6498-110">Requirements</span></span>  
 <span data-ttu-id="e6498-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6498-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6498-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6498-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6498-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6498-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6498-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6498-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
