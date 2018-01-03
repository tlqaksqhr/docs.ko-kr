---
title: "ICLRDebuggingLibraryProvider 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider
helpviewer_keywords: ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7320bf261f28fed85c44f2550df5ecd06421290
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="a7496-102">ICLRDebuggingLibraryProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7496-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="a7496-103">에 포함 되어는 [ProvideLibrary 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) 메서드 라이브러리 공급자 콜백 인터페이스 공용 언어 런타임 버전별 디버깅 라이브러리를 찾아서에 로드할 요청 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7496-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7496-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a7496-104">Methods</span></span>  
  
|<span data-ttu-id="a7496-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a7496-105">Method</span></span>|<span data-ttu-id="a7496-106">설명</span><span class="sxs-lookup"><span data-stu-id="a7496-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7496-107">ProvideLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="a7496-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="a7496-108">디버그 라이브러리를 로드 하는 데 사용할 수 있는 모듈에 대 한 핸들을 제공 하기 위해 디버거에서 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7496-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7496-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7496-109">Requirements</span></span>  
 <span data-ttu-id="a7496-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7496-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7496-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7496-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7496-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7496-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7496-113">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7496-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7496-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7496-114">See Also</span></span>  
 [<span data-ttu-id="a7496-115">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7496-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a7496-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="a7496-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
