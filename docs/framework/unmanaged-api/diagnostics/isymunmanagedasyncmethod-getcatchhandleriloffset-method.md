---
title: "ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96040ee5f56ade3647367c4b879c8aa9e7f460fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="d3422-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d3422-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="d3422-103">참조 [DefineCatchHandlerILOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3422-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3422-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3422-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3422-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3422-105">Parameters</span></span>  
  
|<span data-ttu-id="d3422-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3422-106">Parameter</span></span>|<span data-ttu-id="d3422-107">설명</span><span class="sxs-lookup"><span data-stu-id="d3422-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d3422-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d3422-108">Return Value</span></span>  
 <span data-ttu-id="d3422-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3422-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3422-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3422-110">Requirements</span></span>  
 <span data-ttu-id="d3422-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3422-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3422-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3422-112">See Also</span></span>  
 [<span data-ttu-id="d3422-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3422-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
