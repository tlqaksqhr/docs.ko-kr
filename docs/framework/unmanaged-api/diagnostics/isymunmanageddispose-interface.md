---
title: "ISymUnmanagedDispose 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c7431e7c0e40fe631cf525a961f8bc2710e716d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="290c1-102">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="290c1-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="290c1-103">관리 되지 않는 리소스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="290c1-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="290c1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="290c1-104">Methods</span></span>  
  
|<span data-ttu-id="290c1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="290c1-105">Method</span></span>|<span data-ttu-id="290c1-106">설명</span><span class="sxs-lookup"><span data-stu-id="290c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="290c1-107">Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="290c1-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="290c1-108">이 인해 기본 개체가 모든 내부 참조를 해제 하 고 이후의 모든 메서드 호출 시 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="290c1-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="290c1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="290c1-109">Requirements</span></span>  
 <span data-ttu-id="290c1-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="290c1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290c1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="290c1-111">See Also</span></span>  
 [<span data-ttu-id="290c1-112">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="290c1-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
