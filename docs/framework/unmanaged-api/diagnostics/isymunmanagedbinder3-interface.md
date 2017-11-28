---
title: "ISymUnmanagedBinder3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3 Interface
helpviewer_keywords: ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: df5cd6d4015fad1baf98909ee9cc923cd9bce05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="dfffc-102">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfffc-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="dfffc-103">기호 바인더 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffc-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="dfffc-104">이 인터페이스를 호출 하 여 가져올 `QueryInterface` 구현 하는 개체에는 `ISymUnmanagedBinder` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffc-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfffc-105">것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffc-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfffc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="dfffc-106">Methods</span></span>  
  
|<span data-ttu-id="dfffc-107">메서드</span><span class="sxs-lookup"><span data-stu-id="dfffc-107">Method</span></span>|<span data-ttu-id="dfffc-108">설명</span><span class="sxs-lookup"><span data-stu-id="dfffc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfffc-109">GetReaderFromCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="dfffc-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="dfffc-110">구현 하거나 콜백을 통해 하거나 제공을 사용 하면 프로그램 `IID_IDiaReadExeAtRVACallback` 또는 `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="dfffc-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfffc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfffc-111">Requirements</span></span>  
 <span data-ttu-id="dfffc-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dfffc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfffc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfffc-113">See Also</span></span>  
 [<span data-ttu-id="dfffc-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfffc-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="dfffc-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfffc-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="dfffc-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfffc-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
