---
title: ISymUnmanagedBinder3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06a4d5b1b108c15fa7ee4a7f5270b73f7adc1e6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426344"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="4e0eb-102">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0eb-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="4e0eb-103">기호 바인더 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0eb-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="4e0eb-104">이 인터페이스를 호출 하 여 가져올 `QueryInterface` 구현 하는 개체에는 `ISymUnmanagedBinder` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0eb-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e0eb-105">것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0eb-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e0eb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4e0eb-106">Methods</span></span>  
  
|<span data-ttu-id="4e0eb-107">메서드</span><span class="sxs-lookup"><span data-stu-id="4e0eb-107">Method</span></span>|<span data-ttu-id="4e0eb-108">설명</span><span class="sxs-lookup"><span data-stu-id="4e0eb-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e0eb-109">GetReaderFromCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="4e0eb-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="4e0eb-110">구현 하거나 콜백을 통해 하거나 제공을 사용 하면 프로그램 `IID_IDiaReadExeAtRVACallback` 또는 `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="4e0eb-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e0eb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e0eb-111">Requirements</span></span>  
 <span data-ttu-id="4e0eb-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e0eb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0eb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e0eb-113">See Also</span></span>  
 [<span data-ttu-id="4e0eb-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0eb-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="4e0eb-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0eb-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="4e0eb-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0eb-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
