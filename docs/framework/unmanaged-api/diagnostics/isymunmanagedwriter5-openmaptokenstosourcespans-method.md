---
title: "ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f226a71ac6381c8ca04093beb1d9772d6e6c75e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="f8c85-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="f8c85-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="f8c85-103">토큰 소스 범위 매핑 정보를 내보내는 데 특별 한 사용자 지정 데이터 섹션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f8c85-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="f8c85-104">가 이미 열려 메서드나 그 반대의 경우는 오류 시이 섹션을 열어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8c85-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8c85-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8c85-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f8c85-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="f8c85-106">Return Value</span></span>  
 <span data-ttu-id="f8c85-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f8c85-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c85-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8c85-108">Requirements</span></span>  
 <span data-ttu-id="f8c85-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8c85-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c85-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8c85-110">See Also</span></span>  
 [<span data-ttu-id="f8c85-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8c85-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
