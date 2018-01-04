---
title: "ISymUnmanagedNamespace 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace
helpviewer_keywords: ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1acca300362162b94410aadb10b123b4ecacc664
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="bc0f5-102">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc0f5-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="bc0f5-103">네임 스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc0f5-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc0f5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="bc0f5-104">Methods</span></span>  
  
|<span data-ttu-id="bc0f5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bc0f5-105">Method</span></span>|<span data-ttu-id="bc0f5-106">설명</span><span class="sxs-lookup"><span data-stu-id="bc0f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc0f5-107">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="bc0f5-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="bc0f5-108">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc0f5-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="bc0f5-109">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="bc0f5-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="bc0f5-110">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc0f5-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="bc0f5-111">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="bc0f5-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="bc0f5-112">이 네임 스페이스 내에서 전역 범위에서 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0f5-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc0f5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc0f5-113">Requirements</span></span>  
 <span data-ttu-id="bc0f5-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bc0f5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0f5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc0f5-115">See Also</span></span>  
 [<span data-ttu-id="bc0f5-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc0f5-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
