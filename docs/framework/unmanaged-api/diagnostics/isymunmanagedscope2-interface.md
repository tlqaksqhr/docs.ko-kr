---
title: "ISymUnmanagedScope2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eed6061c8108fcf91f8ac1ac9ff139da426f0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="c3a37-102">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a37-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="c3a37-103">메서드에 들어 있는 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3a37-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="c3a37-104">이 인터페이스를 확장 된 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스 범위 내에서 정의 된 상수에 대 한 정보를 가져오는 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a37-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3a37-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c3a37-105">Methods</span></span>  
  
|<span data-ttu-id="c3a37-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c3a37-106">Method</span></span>|<span data-ttu-id="c3a37-107">설명</span><span class="sxs-lookup"><span data-stu-id="c3a37-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3a37-108">GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c3a37-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="c3a37-109">이 범위 내에서 정의 된 상수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3a37-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="c3a37-110">GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="c3a37-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="c3a37-111">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3a37-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3a37-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3a37-112">Requirements</span></span>  
 <span data-ttu-id="c3a37-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3a37-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a37-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3a37-114">See Also</span></span>  
 [<span data-ttu-id="c3a37-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a37-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c3a37-116">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a37-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
