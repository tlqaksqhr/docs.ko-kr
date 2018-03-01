---
title: "ISymUnmanagedMethod::GetNamespace 메서드"
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
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2244229b50a9944cefb5804720198bf391fd0e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="1ae32-102">ISymUnmanagedMethod::GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="1ae32-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="1ae32-103">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ae32-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae32-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ae32-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ae32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ae32-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1ae32-106">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae32-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ae32-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ae32-107">Return Value</span></span>  
 <span data-ttu-id="1ae32-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ae32-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae32-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ae32-109">Requirements</span></span>  
 <span data-ttu-id="1ae32-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1ae32-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae32-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ae32-111">See Also</span></span>  
 [<span data-ttu-id="1ae32-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ae32-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
