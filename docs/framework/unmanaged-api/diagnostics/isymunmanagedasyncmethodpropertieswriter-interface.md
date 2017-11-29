---
title: "ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd84ea5ee00df3e59d4907cdf97bc36b7f06d993
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="73b65-102">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73b65-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="73b65-103">각 메서드 기호에 대 한 선택적 async 메서드 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="73b65-104">항상 열려 있는 메서드를 함께 사용 즉, 호출 하는 사이 [OpenMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) 및 [CloseMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b65-105">구문</span><span class="sxs-lookup"><span data-stu-id="73b65-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="73b65-106">메서드</span><span class="sxs-lookup"><span data-stu-id="73b65-106">Methods</span></span>  
 <span data-ttu-id="73b65-107">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="73b65-108">메서드</span><span class="sxs-lookup"><span data-stu-id="73b65-108">Method</span></span>|<span data-ttu-id="73b65-109">설명</span><span class="sxs-lookup"><span data-stu-id="73b65-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73b65-110">DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="73b65-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="73b65-111">비동기의 그룹을 정의 현재 메서드에 대 한 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="73b65-112">각 yield 오프셋 잠재적인 yield 식별 하는 await 반환 명령을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="73b65-113">각 `breakpointMethod` / `breakpointOffset` 쌍 식별 비동기 작업은 다시 시작, 다른 방법을에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="73b65-114">DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="73b65-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="73b65-115">IL 비동기 메서드를 래핑하는 컴파일러에서 생성 된 catch 처리기에 대 한 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="73b65-116">생성 된 catch의 IL 오프셋 사용자 코드 메서드에서 발생할 수 있는 경우에 사용자가 아닌 코드 처럼 catch를 처리 하는 디버거에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="73b65-117">특히 사용에 대 한 응답을 **CatchHandlerFound** 예외 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="73b65-118">DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="73b65-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="73b65-119">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b65-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73b65-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73b65-120">Requirements</span></span>  
 <span data-ttu-id="73b65-121">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73b65-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b65-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73b65-122">See Also</span></span>  
 [<span data-ttu-id="73b65-123">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73b65-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
