---
title: "ISymUnmanagedMethod::GetScopeFromOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetScopeFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 890fd702bc2edb5714dc9c91a618c6420a11a27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="448a2-102">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="448a2-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="448a2-103">지정된 된 오프셋을 포함 하는이 메서드 내에서 최대 포함 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="448a2-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="448a2-104">지역 변수 검색을 시작 데 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a2-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="448a2-105">구문</span><span class="sxs-lookup"><span data-stu-id="448a2-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="448a2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="448a2-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="448a2-107">[in] A `ULONG` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="448a2-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="448a2-108">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="448a2-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="448a2-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="448a2-109">Return Value</span></span>  
 <span data-ttu-id="448a2-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="448a2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="448a2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="448a2-111">Requirements</span></span>  
 <span data-ttu-id="448a2-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="448a2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448a2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448a2-113">See Also</span></span>  
 [<span data-ttu-id="448a2-114">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="448a2-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
