---
title: "CorErrorIfEmitOutOfOrder 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="c0c5d-102">CorErrorIfEmitOutOfOrder 열거형</span><span class="sxs-lookup"><span data-stu-id="c0c5d-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="c0c5d-103">메타데이터를 내보내는 순서가 잘못되었을 때 오류 메시지가 생성되어야 하는 조건을 나타내는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0c5d-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="c0c5d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c0c5d-105">Members</span></span>  
  
|<span data-ttu-id="c0c5d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c0c5d-106">Member</span></span>|<span data-ttu-id="c0c5d-107">설명</span><span class="sxs-lookup"><span data-stu-id="c0c5d-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="c0c5d-108">오류 메시지를 표시 하지 않는 기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="c0c5d-109">컴파일러 오류 메시지를 생성 하지 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="c0c5d-110">필드, 속성, 이벤트, 메서드 때 컴파일러에서 오류 메시지를 생성 하도록 하거나 매개 변수 순서가 내보내집니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="c0c5d-111">메서드에 잘못 된 순서로 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="c0c5d-112">필드는 내보내는 순서가 잘못 되었을 때 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="c0c5d-113">매개 변수가 잘못 된 순서로 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="c0c5d-114">속성은 내보내는 순서가 잘못 되었을 때 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="c0c5d-115">이벤트가 잘못 된 순서로 발생 하는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0c5d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0c5d-116">Requirements</span></span>  
 <span data-ttu-id="c0c5d-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0c5d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c5d-118">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c0c5d-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c0c5d-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c5d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c5d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0c5d-120">See Also</span></span>  
 [<span data-ttu-id="c0c5d-121">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c0c5d-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
