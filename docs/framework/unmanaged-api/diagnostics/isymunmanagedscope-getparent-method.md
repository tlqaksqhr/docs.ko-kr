---
title: "ISymUnmanagedScope::GetParent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1defb0f95ed38d8dbe5d47d804e340b3ca35a79c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="68b23-102">ISymUnmanagedScope::GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="68b23-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="68b23-103">이 범위의 상위 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68b23-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b23-104">구문</span><span class="sxs-lookup"><span data-stu-id="68b23-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68b23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68b23-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="68b23-106">[out] 반환 된에 대 한 포인터 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="68b23-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68b23-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="68b23-107">Return Value</span></span>  
 <span data-ttu-id="68b23-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="68b23-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b23-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68b23-109">Requirements</span></span>  
 <span data-ttu-id="68b23-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68b23-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b23-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68b23-111">See Also</span></span>  
 [<span data-ttu-id="68b23-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68b23-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="68b23-113">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="68b23-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
