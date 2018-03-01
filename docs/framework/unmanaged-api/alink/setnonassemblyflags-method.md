---
title: "SetNonAssemblyFlags 메서드"
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
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e944f285ee0925b76fdd9b95c824deee38cead2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="beb8f-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="beb8f-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="beb8f-103">어셈블리와 관련 되지 않는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb8f-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="beb8f-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="beb8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="beb8f-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="beb8f-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="beb8f-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="beb8f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="beb8f-107">Return Value</span></span>  
 <span data-ttu-id="beb8f-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb8f-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb8f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="beb8f-109">Requirements</span></span>  
 <span data-ttu-id="beb8f-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="beb8f-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb8f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beb8f-111">See Also</span></span>  
 [<span data-ttu-id="beb8f-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="beb8f-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="beb8f-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="beb8f-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="beb8f-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="beb8f-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
