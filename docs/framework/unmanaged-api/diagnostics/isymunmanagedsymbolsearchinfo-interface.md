---
title: "ISymUnmanagedSymbolSearchInfo 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 441330471906a891646ad55eb73ec25b44800cbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="6df1d-102">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6df1d-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="6df1d-103">검색 경로 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df1d-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="6df1d-104">이 인터페이스를 호출 하 여 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6df1d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6df1d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6df1d-105">Methods</span></span>  
  
|<span data-ttu-id="6df1d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6df1d-106">Method</span></span>|<span data-ttu-id="6df1d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6df1d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6df1d-108">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="6df1d-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="6df1d-109">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6df1d-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="6df1d-110">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="6df1d-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="6df1d-111">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6df1d-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="6df1d-112">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="6df1d-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="6df1d-113">검색 경로 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6df1d-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6df1d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6df1d-114">Requirements</span></span>  
 <span data-ttu-id="6df1d-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6df1d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df1d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6df1d-116">See Also</span></span>  
 [<span data-ttu-id="6df1d-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6df1d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
