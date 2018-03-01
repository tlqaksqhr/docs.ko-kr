---
title: "ISymUnmanagedWriter::CloseNamespace 메서드"
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
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 364c2a851371ea147a61a49826efe702140c5b2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="657ed-102">ISymUnmanagedWriter::CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="657ed-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="657ed-103">가장 최근에 닫히는 네임 스페이스를 열.</span><span class="sxs-lookup"><span data-stu-id="657ed-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="657ed-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="657ed-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="657ed-105">Return Value</span></span>  
 <span data-ttu-id="657ed-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="657ed-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="657ed-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="657ed-107">Requirements</span></span>  
 <span data-ttu-id="657ed-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="657ed-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657ed-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="657ed-109">See Also</span></span>  
 [<span data-ttu-id="657ed-110">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="657ed-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="657ed-111">OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="657ed-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
