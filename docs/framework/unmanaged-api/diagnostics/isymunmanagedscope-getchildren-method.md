---
title: "ISymUnmanagedScope::GetChildren 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetChildren
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2259eccc3be68f562a0c5b00ffe7fd47bad9a238
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="aae62-102">ISymUnmanagedScope::GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="aae62-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="aae62-103">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aae62-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae62-104">구문</span><span class="sxs-lookup"><span data-stu-id="aae62-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aae62-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aae62-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="aae62-106">[in] A `ULONG32` 크기를 표시 하는 `children` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aae62-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="aae62-107">[out] 에 대 한 포인터는 `ULONG32` 자식을 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae62-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="aae62-108">[out] 자식 항목의 반환 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aae62-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aae62-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="aae62-109">Return Value</span></span>  
 <span data-ttu-id="aae62-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="aae62-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae62-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aae62-111">Requirements</span></span>  
 <span data-ttu-id="aae62-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aae62-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae62-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aae62-113">See Also</span></span>  
 [<span data-ttu-id="aae62-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aae62-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="aae62-115">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="aae62-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
