---
title: "ISymUnmanagedReader2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="192c3-102">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="192c3-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="192c3-103">문서, 메서드 및 기호 저장소 내의 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="192c3-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="192c3-104">이 인터페이스에서 확장 된 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="192c3-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="192c3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="192c3-105">Methods</span></span>  
  
|<span data-ttu-id="192c3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="192c3-106">Method</span></span>|<span data-ttu-id="192c3-107">설명</span><span class="sxs-lookup"><span data-stu-id="192c3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="192c3-108">GetMethodByVersionPreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="192c3-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="192c3-109">메서드 토큰이 편집 하며 계속 하기 버전 번호를 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="192c3-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="192c3-110">GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="192c3-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="192c3-111">줄 정보를 제공된 된 문서에 있는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="192c3-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="192c3-112">GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="192c3-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="192c3-113">이름을 기반으로 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="192c3-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="192c3-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="192c3-114">Requirements</span></span>  
 <span data-ttu-id="192c3-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="192c3-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192c3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="192c3-116">See Also</span></span>  
 [<span data-ttu-id="192c3-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="192c3-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="192c3-118">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="192c3-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
