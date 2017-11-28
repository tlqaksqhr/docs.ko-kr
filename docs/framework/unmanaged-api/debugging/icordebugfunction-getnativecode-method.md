---
title: "ICorDebugFunction::GetNativeCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetNativeCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fccfaeb346d59f5cf565f47a9a64e732706adad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="6c27b-102">ICorDebugFunction::GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="6c27b-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="6c27b-103">이 ICorDebugFunction 인스턴스에서 나타내는 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c27b-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c27b-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c27b-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c27b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c27b-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="6c27b-106">[out] 이 함수는 Microsoft MSIL (intermediate language) 코드에서 적시 (JIT) 컴파일된 되지 않은 경우이 함수 또는 null에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c27b-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c27b-107">설명</span><span class="sxs-lookup"><span data-stu-id="6c27b-107">Remarks</span></span>  
 <span data-ttu-id="6c27b-108">경우이 나타내는 함수 `ICorDebugFunction` 인스턴스가 되었습니다 JIT 컴파일된 두 번 이상 제네릭 형식으로의 경우 처럼 `GetNativeCode` 네이티브 코드를 임의의 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c27b-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c27b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c27b-109">Requirements</span></span>  
 <span data-ttu-id="6c27b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c27b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c27b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c27b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c27b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c27b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c27b-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c27b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
