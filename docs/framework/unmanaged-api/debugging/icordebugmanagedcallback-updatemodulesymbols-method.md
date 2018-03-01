---
title: "ICorDebugManagedCallback::UpdateModuleSymbols 메서드"
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
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad5a84268f3810a1fb73a21a6bd8106e82ccbd78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="d23fb-102">ICorDebugManagedCallback::UpdateModuleSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="d23fb-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="d23fb-103">공용 언어 런타임 모듈에 대 한 기호 변경 되었다는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="d23fb-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d23fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d23fb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d23fb-106">[in] 기호 변경 되었습니다 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="d23fb-107">[in] 모듈의 기호가 변경 되었음을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="d23fb-108">[in] Win32 COM에 대 한 포인터 `IStream` 수정 된 기호를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d23fb-109">설명</span><span class="sxs-lookup"><span data-stu-id="d23fb-109">Remarks</span></span>  
 <span data-ttu-id="d23fb-110">이 메서드를 호출 하 여 모듈의 기호의 디버거 뷰를 업데이트할 수 있게 [isymunmanagedreader:: Updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 또는 [isymunmanagedreader:: Replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="d23fb-111">이 콜백은 같은 모듈에 대 한 여러 번 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="d23fb-112">디버거는 바인딩되지 않은 소스 수준 중단점을 바인딩할 시도해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="d23fb-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23fb-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d23fb-113">Requirements</span></span>  
 <span data-ttu-id="d23fb-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d23fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23fb-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d23fb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d23fb-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23fb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23fb-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23fb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23fb-118">See Also</span></span>  
 [<span data-ttu-id="d23fb-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d23fb-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
