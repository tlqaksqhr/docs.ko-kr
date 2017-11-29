---
title: "ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e017097183243c84a2ce40cc473067e05c80c3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="9069f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="9069f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="9069f-103">참조 [DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9069f-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9069f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9069f-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9069f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9069f-105">Parameters</span></span>  
  
|<span data-ttu-id="9069f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9069f-106">Parameter</span></span>|<span data-ttu-id="9069f-107">설명</span><span class="sxs-lookup"><span data-stu-id="9069f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9069f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9069f-108">Return Value</span></span>  
 <span data-ttu-id="9069f-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9069f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9069f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9069f-110">Requirements</span></span>  
 <span data-ttu-id="9069f-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9069f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9069f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9069f-112">See Also</span></span>  
 [<span data-ttu-id="9069f-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9069f-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
