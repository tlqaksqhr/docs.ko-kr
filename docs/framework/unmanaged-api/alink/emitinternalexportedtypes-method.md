---
title: "EmitInternalExportedTypes 메서드"
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
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48ad5e34b926cf3dab562f57bb9206fa0ba70e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="c7b2b-102">EmitInternalExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="c7b2b-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="c7b2b-103">어셈블리에 추가 된 형식을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7b2b-103">Emits types added to the assembly.</span></span> <span data-ttu-id="c7b2b-104">알려진 내부 형식이 추가 된 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b2b-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b2b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7b2b-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7b2b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7b2b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c7b2b-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b2b-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7b2b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7b2b-108">Return Value</span></span>  
 <span data-ttu-id="c7b2b-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b2b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7b2b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7b2b-110">Requirements</span></span>  
 <span data-ttu-id="c7b2b-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="c7b2b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b2b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7b2b-112">See Also</span></span>  
 [<span data-ttu-id="c7b2b-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7b2b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c7b2b-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7b2b-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c7b2b-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="c7b2b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
