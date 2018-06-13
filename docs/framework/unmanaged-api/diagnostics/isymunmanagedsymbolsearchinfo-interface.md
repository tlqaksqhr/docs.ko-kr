---
title: ISymUnmanagedSymbolSearchInfo 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dce9653d3fef534ac6567e36a4c8213e13ab231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429171"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="63c86-102">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63c86-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="63c86-103">검색 경로 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c86-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="63c86-104">이 인터페이스를 호출 하 여 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="63c86-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63c86-105">메서드</span><span class="sxs-lookup"><span data-stu-id="63c86-105">Methods</span></span>  
  
|<span data-ttu-id="63c86-106">메서드</span><span class="sxs-lookup"><span data-stu-id="63c86-106">Method</span></span>|<span data-ttu-id="63c86-107">설명</span><span class="sxs-lookup"><span data-stu-id="63c86-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63c86-108">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="63c86-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="63c86-109">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63c86-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="63c86-110">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="63c86-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="63c86-111">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63c86-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="63c86-112">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="63c86-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="63c86-113">검색 경로 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63c86-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63c86-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63c86-114">Requirements</span></span>  
 <span data-ttu-id="63c86-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63c86-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c86-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63c86-116">See Also</span></span>  
 [<span data-ttu-id="63c86-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63c86-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
