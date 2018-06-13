---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425433"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="ee367-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ee367-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="ee367-103">IL 비동기 메서드를 래핑하는 컴파일러에서 생성 된 catch 처리기에 대 한 오프셋을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee367-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="ee367-104">생성 된 catch의 IL 오프셋을 마치 사용자 코드가 아닌 사용자 코드 메서드에서 발생할 수 있는 경우에 catch를 처리 하는 디버거에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee367-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="ee367-105">특히 사용에 대 한 응답을 **CatchHandlerFound** 예외 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ee367-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee367-106">구문</span><span class="sxs-lookup"><span data-stu-id="ee367-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee367-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee367-107">Parameters</span></span>  
  
|<span data-ttu-id="ee367-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee367-108">Parameter</span></span>|<span data-ttu-id="ee367-109">설명</span><span class="sxs-lookup"><span data-stu-id="ee367-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="ee367-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ee367-110">Return Value</span></span>  
 <span data-ttu-id="ee367-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ee367-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee367-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee367-112">Requirements</span></span>  
 <span data-ttu-id="ee367-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee367-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee367-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee367-114">See Also</span></span>  
 [<span data-ttu-id="ee367-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee367-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
