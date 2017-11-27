---
title: "ISymENCUnmanagedMethod 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod
helpviewer_keywords: ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68929dc30b029133c73f18c3749f39f014359c0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="023cb-102">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="023cb-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="023cb-103">편집 하며 계속 하기 기능에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="023cb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-104">Methods</span></span>  
  
|<span data-ttu-id="023cb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-105">Method</span></span>|<span data-ttu-id="023cb-106">설명</span><span class="sxs-lookup"><span data-stu-id="023cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="023cb-107">GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="023cb-108">이 메서드에 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="023cb-109">GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="023cb-110">이 메서드에 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="023cb-111">GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="023cb-112">오프셋와 관련 된 선에 대 한 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="023cb-113">GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="023cb-114">오프셋와 관련 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="023cb-115">GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="023cb-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="023cb-116">가장 작은 가져옵니다 특정 문서에서 줄 및 메서드에 대 한 가장 큰 끝 줄을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="023cb-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="023cb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="023cb-117">Requirements</span></span>  
 <span data-ttu-id="023cb-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="023cb-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023cb-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="023cb-119">See Also</span></span>  
 [<span data-ttu-id="023cb-120">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="023cb-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
