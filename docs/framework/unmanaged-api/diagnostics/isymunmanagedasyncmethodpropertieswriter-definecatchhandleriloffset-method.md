---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54cc369b309d1ffe20d0f3e6a2d4ae4e0443c85f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="63a02-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="63a02-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="63a02-103">IL 비동기 메서드를 래핑하는 컴파일러에서 생성 된 catch 처리기에 대 한 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a02-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="63a02-104">생성 된 catch의 IL 오프셋을 마치 사용자 코드가 아닌 사용자 코드 메서드에서 발생할 수 있는 경우에 catch를 처리 하는 디버거에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63a02-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="63a02-105">특히 사용에 대 한 응답을 **CatchHandlerFound** 예외 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="63a02-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a02-106">구문</span><span class="sxs-lookup"><span data-stu-id="63a02-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63a02-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63a02-107">Parameters</span></span>  
  
|<span data-ttu-id="63a02-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63a02-108">Parameter</span></span>|<span data-ttu-id="63a02-109">설명</span><span class="sxs-lookup"><span data-stu-id="63a02-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="63a02-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="63a02-110">Return Value</span></span>  
 <span data-ttu-id="63a02-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63a02-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63a02-112">Requirements</span></span>  
 <span data-ttu-id="63a02-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63a02-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a02-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63a02-114">See Also</span></span>  
 [<span data-ttu-id="63a02-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63a02-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
