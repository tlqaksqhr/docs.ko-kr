---
title: "ISymUnmanagedWriter5 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c5ac543ad98cc14382f0fb6d0d04fafa7136136e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="4fdc4-102">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fdc4-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="4fdc4-103">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fdc4-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fdc4-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="4fdc4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4fdc4-105">Methods</span></span>  
 <span data-ttu-id="4fdc4-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="4fdc4-107">메서드</span><span class="sxs-lookup"><span data-stu-id="4fdc4-107">Method</span></span>|<span data-ttu-id="4fdc4-108">설명</span><span class="sxs-lookup"><span data-stu-id="4fdc4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fdc4-109">CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="4fdc4-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="4fdc4-110">매핑 정보 토큰 소스 범위에 대 한 특수 한 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="4fdc4-111">이 닫힌 후에 매핑 정보가 더 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="4fdc4-112">MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="4fdc4-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="4fdc4-113">지도 지정 된 소스 줄에 지정 된 메타 데이터 토큰 지정 된 소스 파일에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="4fdc4-114">호출 하는 사이 호출 해야 [OpenMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="4fdc4-115">OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="4fdc4-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="4fdc4-116">토큰 소스 범위 매핑 정보를 내보내는 데 특별 한 사용자 지정 데이터 섹션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="4fdc4-117">가 이미 열려 메서드나 그 반대의 경우는 오류 시이 섹션을 열어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fdc4-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fdc4-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fdc4-118">Requirements</span></span>  
 <span data-ttu-id="4fdc4-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4fdc4-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdc4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fdc4-120">See Also</span></span>  
 [<span data-ttu-id="4fdc4-121">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fdc4-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="4fdc4-122">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fdc4-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
