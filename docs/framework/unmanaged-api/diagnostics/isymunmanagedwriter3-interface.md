---
title: ISymUnmanagedWriter3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1315d54e93769772772d536e9688c754a96c67c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429396"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="f0902-102">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0902-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="f0902-103">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0902-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f0902-104">이 인터페이스에서 확장 된 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f0902-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0902-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f0902-105">Methods</span></span>  
  
|<span data-ttu-id="f0902-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f0902-106">Method</span></span>|<span data-ttu-id="f0902-107">설명</span><span class="sxs-lookup"><span data-stu-id="f0902-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0902-108">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="f0902-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="f0902-109">스트림에 지금까지 작성 된 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f0902-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="f0902-110">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="f0902-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="f0902-111">메서드를 열고 하 고 이미지에 해당 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0902-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0902-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0902-112">Requirements</span></span>  
 <span data-ttu-id="f0902-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f0902-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0902-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0902-114">See Also</span></span>  
 [<span data-ttu-id="f0902-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0902-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f0902-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0902-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="f0902-117">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0902-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
