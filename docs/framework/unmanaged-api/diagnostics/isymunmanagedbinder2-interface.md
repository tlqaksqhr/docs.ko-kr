---
title: "ISymUnmanagedBinder2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c276f0abedf4ccab92770af649a8dd0afb6d39d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="ccd7f-102">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd7f-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="ccd7f-103">비관리 코드의 기호 바인더를 나타내며 확장는 [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ccd7f-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ccd7f-104">것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd7f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccd7f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ccd7f-105">Methods</span></span>  
  
|<span data-ttu-id="ccd7f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ccd7f-106">Method</span></span>|<span data-ttu-id="ccd7f-107">설명</span><span class="sxs-lookup"><span data-stu-id="ccd7f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccd7f-108">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="ccd7f-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="ccd7f-109">메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스를 모듈와 관련 된 디버깅 기호를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd7f-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="ccd7f-110">보다 더욱 광범위 한 검색을 제공 된 [isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccd7f-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccd7f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccd7f-111">Requirements</span></span>  
 <span data-ttu-id="ccd7f-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ccd7f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd7f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccd7f-113">See Also</span></span>  
 [<span data-ttu-id="ccd7f-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd7f-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="ccd7f-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd7f-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="ccd7f-116">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd7f-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
