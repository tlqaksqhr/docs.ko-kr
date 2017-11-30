---
title: "ISymUnmanagedBinder 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 00b0b5ee330a606ae7417185a804f3d37ab6664a
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="e1b5e-102">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1b5e-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="e1b5e-103">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1b5e-104">것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1b5e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e1b5e-105">Methods</span></span>  
  
|<span data-ttu-id="e1b5e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e1b5e-106">Method</span></span>|<span data-ttu-id="e1b5e-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1b5e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1b5e-108">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e1b5e-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="e1b5e-109">메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조는 모듈에 연결 된 디버깅 기호는 읽기입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="e1b5e-110">GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="e1b5e-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="e1b5e-111">제공 되는 메타 데이터 인터페이스와 기호 저장소를 포함 하는 스트림을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 디버깅 읽을 구조에서 지정 된 기호 저장소 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b5e-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1b5e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1b5e-112">Requirements</span></span>  
 <span data-ttu-id="e1b5e-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e1b5e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b5e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1b5e-114">See Also</span></span>  
 [<span data-ttu-id="e1b5e-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1b5e-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="e1b5e-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1b5e-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="e1b5e-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1b5e-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
