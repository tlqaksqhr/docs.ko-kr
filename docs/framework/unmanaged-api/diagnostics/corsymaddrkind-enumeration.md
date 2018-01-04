---
title: "CorSymAddrKind 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymAddrKind
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymAddrKind
helpviewer_keywords: CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 300913f9ea89044e425f9f05856d13fa15cdc015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="5509e-102">CorSymAddrKind 열거형</span><span class="sxs-lookup"><span data-stu-id="5509e-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="5509e-103">메모리 주소 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5509e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5509e-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="5509e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5509e-105">Members</span></span>  
  
|<span data-ttu-id="5509e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5509e-106">Member</span></span>|<span data-ttu-id="5509e-107">설명</span><span class="sxs-lookup"><span data-stu-id="5509e-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="5509e-108">가 Microsoft MSIL (intermediate language) 지역 변수 또는 매개 변수 인덱스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="5509e-109">모듈에 상대 가상 주소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="5509e-110">CPU 레지스터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="5509e-111">첫 번째 주소는 레지스터와 두 번째 주소는 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="5509e-112">기본 주소에서의 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="5509e-113">첫 번째 주소는 하위 부분이 있으면 레지스터의 두 번째 주소는 높은 부분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="5509e-114">첫 번째 주소는 레지스터의 하위 부분이, 두 번째는 높은 부분 및 세 번째는 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="5509e-115">첫 번째 주소는 레지스터는 오프셋, 두 번째 및 세 번째는 레지스터의 많은 부분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="5509e-116">첫 번째 주소는 필드의 시작 및 두 번째 주소는 필드 길이 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="5509e-117">첫 번째 주소 섹션은 두 번째 주소는 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5509e-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5509e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5509e-118">Requirements</span></span>  
 <span data-ttu-id="5509e-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5509e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5509e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5509e-120">See Also</span></span>  
 [<span data-ttu-id="5509e-121">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="5509e-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
