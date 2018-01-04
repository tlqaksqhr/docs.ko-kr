---
title: "ISymUnmanagedWriter::CloseMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21c4cdd42613f5e8b60c39426b4f169a034ce7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="3dcc4-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3dcc4-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="3dcc4-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc4-103">Closes the current method.</span></span> <span data-ttu-id="3dcc4-104">메서드를 닫은 후 내에서 더 이상 없는 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc4-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dcc4-105">구문</span><span class="sxs-lookup"><span data-stu-id="3dcc4-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3dcc4-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="3dcc4-106">Return Value</span></span>  
 <span data-ttu-id="3dcc4-107">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3dcc4-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dcc4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dcc4-108">Requirements</span></span>  
 <span data-ttu-id="3dcc4-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3dcc4-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dcc4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dcc4-110">See Also</span></span>  
 [<span data-ttu-id="3dcc4-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dcc4-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="3dcc4-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3dcc4-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
