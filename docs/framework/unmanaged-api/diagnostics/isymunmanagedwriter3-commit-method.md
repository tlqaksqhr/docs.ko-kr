---
title: "ISymUnmanagedWriter3::커밋 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.Commit
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3ff2baa8a5006e2a3a83ddbcf5ca79b78350794b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="df8db-102">ISymUnmanagedWriter3::커밋 메서드</span><span class="sxs-lookup"><span data-stu-id="df8db-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="df8db-103">스트림에 지금까지 작성 된 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="df8db-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df8db-104">구문</span><span class="sxs-lookup"><span data-stu-id="df8db-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="df8db-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="df8db-105">Return Value</span></span>  
 <span data-ttu-id="df8db-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="df8db-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df8db-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df8db-107">Requirements</span></span>  
 <span data-ttu-id="df8db-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df8db-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df8db-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df8db-109">See Also</span></span>  
 [<span data-ttu-id="df8db-110">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df8db-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
