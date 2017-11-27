---
title: "CorValidatorModuleType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorValidatorModuleType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorValidatorModuleType
helpviewer_keywords: CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa7ca08398358dcf00a986c356de365e9caafc4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="dd5f3-102">CorValidatorModuleType 열거형</span><span class="sxs-lookup"><span data-stu-id="dd5f3-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="dd5f3-103">모듈의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd5f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd5f3-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="dd5f3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="dd5f3-105">Members</span></span>  
  
|<span data-ttu-id="dd5f3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="dd5f3-106">Member</span></span>|<span data-ttu-id="dd5f3-107">설명</span><span class="sxs-lookup"><span data-stu-id="dd5f3-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="dd5f3-108">모듈에 잘못 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="dd5f3-109">최소 값은 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="dd5f3-110">모듈에는 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="dd5f3-111">모듈은.obj 파일.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="dd5f3-112">모듈은는 편집 하며 계속 하기 디버거 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="dd5f3-113">모듈은 증분 빌드할입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="dd5f3-114">최대값은 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd5f3-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd5f3-115">Requirements</span></span>  
 <span data-ttu-id="dd5f3-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd5f3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd5f3-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd5f3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd5f3-118">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="dd5f3-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd5f3-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd5f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd5f3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd5f3-120">See Also</span></span>  
 [<span data-ttu-id="dd5f3-121">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="dd5f3-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
