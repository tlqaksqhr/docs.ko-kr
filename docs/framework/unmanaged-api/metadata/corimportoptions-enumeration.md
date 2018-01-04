---
title: "CorImportOptions 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorImportOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorImportOptions
helpviewer_keywords: CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9af7bbb6dd7cfa488f72ec99f9cfd848f04e72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="7a515-102">CorImportOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="7a515-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="7a515-103">현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a515-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a515-104">Syntax</span></span>  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="7a515-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7a515-105">Members</span></span>  
  
|<span data-ttu-id="7a515-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7a515-106">Member</span></span>|<span data-ttu-id="7a515-107">설명</span><span class="sxs-lookup"><span data-stu-id="7a515-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="7a515-108">삭제 된 레코드는 건너 뜁니다 하는 기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="7a515-109">모든 메타 데이터를 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="7a515-110">삭제 된 항목을 포함 하 여 모든 형식 정의 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="7a515-111">모든 MethodDefs, 삭제 된 항목을 포함 하 여 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="7a515-112">삭제 된 항목을 포함 하 여 모든 Fielddef 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="7a515-113">모든 PropertyDefs, 삭제 된 항목을 포함 하 여 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="7a515-114">삭제 된 항목을 포함 하 여 모든 Eventdef 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="7a515-115">삭제 된 항목을 포함 하 여 모든 사용자 지정 특성을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="7a515-116">삭제 된 항목을 포함 하는 모든 내보낸된 형식을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a515-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a515-117">Requirements</span></span>  
 <span data-ttu-id="7a515-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a515-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a515-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7a515-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7a515-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a515-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a515-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a515-121">See Also</span></span>  
 [<span data-ttu-id="7a515-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7a515-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
