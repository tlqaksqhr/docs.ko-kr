---
title: "ISymUnmanagedScope::GetLocalCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocalCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db774140ef55b2dfcb54ff701c2b842418a4923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="c0753-102">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c0753-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="c0753-103">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c0753-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0753-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0753-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0753-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0753-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c0753-106">[out] 에 대 한 포인터는 `ULONG32` 지역 변수의 개수를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="c0753-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0753-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c0753-107">Return Value</span></span>  
 <span data-ttu-id="c0753-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c0753-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0753-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0753-109">Requirements</span></span>  
 <span data-ttu-id="c0753-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c0753-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0753-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0753-111">See Also</span></span>  
 [<span data-ttu-id="c0753-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0753-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
