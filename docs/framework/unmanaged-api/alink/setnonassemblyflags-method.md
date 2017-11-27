---
title: "SetNonAssemblyFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetNonAssemblyFlags
api_location: alink.dll
api_type: COM
f1_keywords: SetNonAssemblyFlags
helpviewer_keywords: SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5f8761259e89b4befd0eeaf893ffbe5d4142350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="a228e-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="a228e-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="a228e-103">어셈블리와 관련 되지 않는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a228e-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a228e-104">구문</span><span class="sxs-lookup"><span data-stu-id="a228e-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a228e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a228e-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="a228e-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a228e-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a228e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a228e-107">Return Value</span></span>  
 <span data-ttu-id="a228e-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a228e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a228e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a228e-109">Requirements</span></span>  
 <span data-ttu-id="a228e-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="a228e-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a228e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a228e-111">See Also</span></span>  
 [<span data-ttu-id="a228e-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a228e-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a228e-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a228e-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a228e-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="a228e-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
