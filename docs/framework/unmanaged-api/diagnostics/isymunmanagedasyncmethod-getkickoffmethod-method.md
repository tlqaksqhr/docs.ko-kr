---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424770"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="09002-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="09002-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="09002-103">참조 [DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09002-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09002-104">구문</span><span class="sxs-lookup"><span data-stu-id="09002-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09002-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09002-105">Parameters</span></span>  
  
|<span data-ttu-id="09002-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09002-106">Parameter</span></span>|<span data-ttu-id="09002-107">설명</span><span class="sxs-lookup"><span data-stu-id="09002-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="09002-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="09002-108">Return Value</span></span>  
 <span data-ttu-id="09002-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="09002-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09002-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09002-110">Requirements</span></span>  
 <span data-ttu-id="09002-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="09002-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09002-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09002-112">See Also</span></span>  
 [<span data-ttu-id="09002-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09002-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
