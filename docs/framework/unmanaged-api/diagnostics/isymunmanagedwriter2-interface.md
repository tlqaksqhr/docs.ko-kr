---
title: "ISymUnmanagedWriter2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2
helpviewer_keywords: ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd297a8ee0172f1624e6983de9bc9bf25bd86621
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="8da0d-102">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8da0d-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="8da0d-103">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8da0d-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="8da0d-104">이 인터페이스에서 확장 된 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8da0d-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8da0d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8da0d-105">Methods</span></span>  
  
|<span data-ttu-id="8da0d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8da0d-106">Method</span></span>|<span data-ttu-id="8da0d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8da0d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8da0d-108">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="8da0d-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="8da0d-109">상수 값에 대 한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8da0d-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="8da0d-110">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="8da0d-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="8da0d-111">단일 전역 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8da0d-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="8da0d-112">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="8da0d-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="8da0d-113">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8da0d-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8da0d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8da0d-114">Requirements</span></span>  
 <span data-ttu-id="8da0d-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8da0d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da0d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8da0d-116">See Also</span></span>  
 [<span data-ttu-id="8da0d-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8da0d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="8da0d-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8da0d-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="8da0d-119">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8da0d-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
