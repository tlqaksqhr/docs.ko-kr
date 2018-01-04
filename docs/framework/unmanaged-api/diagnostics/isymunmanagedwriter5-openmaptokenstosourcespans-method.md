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
ms.workload: dotnet
ms.openlocfilehash: cb283198de5621748b37fe8e22f2fbc408754ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="34bd6-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="34bd6-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="34bd6-103">토큰 소스 범위 매핑 정보를 내보내는 데 특별 한 사용자 지정 데이터 섹션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="34bd6-104">가 이미 열려 메서드나 그 반대의 경우는 오류 시이 섹션을 열어 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bd6-105">구문</span><span class="sxs-lookup"><span data-stu-id="34bd6-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="34bd6-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="34bd6-106">Return Value</span></span>  
 <span data-ttu-id="34bd6-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bd6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34bd6-108">Requirements</span></span>  
 <span data-ttu-id="34bd6-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="34bd6-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34bd6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34bd6-110">See Also</span></span>  
 [<span data-ttu-id="34bd6-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34bd6-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
