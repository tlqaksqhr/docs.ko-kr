---
title: ISymUnmanagedAsyncMethod 인터페이스
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cefad27d8b9314b45dec6100e35a54990fb591c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428001"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="a08c8-102">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a08c8-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="a08c8-103">이 인터페이스는 읽기 보완 하 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a08c8-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="a08c8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-105">Methods</span></span>  
 <span data-ttu-id="a08c8-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="a08c8-107">메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-107">Method</span></span>|<span data-ttu-id="a08c8-108">설명</span><span class="sxs-lookup"><span data-stu-id="a08c8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a08c8-109">GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="a08c8-110">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="a08c8-111">GetAsyncStepInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="a08c8-112">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="a08c8-113">GetCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="a08c8-114">참조 [DefineCatchHandlerILOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="a08c8-115">GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="a08c8-116">참조 [DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="a08c8-117">HasCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="a08c8-118">참조 [DefineCatchHandlerILOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="a08c8-119">IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a08c8-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="a08c8-120">여부는 메서드는 비동기 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="a08c8-121">이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 데 유효한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a08c8-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="a08c8-122">모든 return가 `E_UNEXPECTED` 이 경우.</span><span class="sxs-lookup"><span data-stu-id="a08c8-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a08c8-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a08c8-123">Requirements</span></span>  
 <span data-ttu-id="a08c8-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a08c8-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08c8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a08c8-125">See Also</span></span>  
 [<span data-ttu-id="a08c8-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a08c8-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
