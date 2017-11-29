---
title: "CoUninitializeEE 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeEE
helpviewer_keywords: CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d64064c29d2a03578305f71a37e759907814727e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="couninitializeee-function"></a><span data-ttu-id="95cb5-102">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="95cb5-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="95cb5-103">`CoUninitializeEE`사용 되지 않으며 특정 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95cb5-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95cb5-104">구문</span><span class="sxs-lookup"><span data-stu-id="95cb5-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="95cb5-105">설명</span><span class="sxs-lookup"><span data-stu-id="95cb5-105">Remarks</span></span>  
 <span data-ttu-id="95cb5-106">공용 언어 런타임 실행 엔진 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95cb5-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="95cb5-107">실행 엔진 호출을 종료 하려면 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95cb5-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cb5-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95cb5-108">See Also</span></span>  
 [<span data-ttu-id="95cb5-109">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="95cb5-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="95cb5-110">메타 데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="95cb5-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
