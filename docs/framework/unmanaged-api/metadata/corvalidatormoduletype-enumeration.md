---
title: CorValidatorModuleType 열거형
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97e9ae5a7c35b4f9b6e2b4ca7e754b5b7480dfa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444141"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="5b7b6-102">CorValidatorModuleType 열거형</span><span class="sxs-lookup"><span data-stu-id="5b7b6-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="5b7b6-103">모듈의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b7b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b7b6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5b7b6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5b7b6-105">Members</span></span>  
  
|<span data-ttu-id="5b7b6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5b7b6-106">Member</span></span>|<span data-ttu-id="5b7b6-107">설명</span><span class="sxs-lookup"><span data-stu-id="5b7b6-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="5b7b6-108">모듈에 잘못 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="5b7b6-109">최소 값은 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="5b7b6-110">모듈에는 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="5b7b6-111">모듈은.obj 파일.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="5b7b6-112">모듈은는 편집 하며 계속 하기 디버거 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="5b7b6-113">모듈은 증분 빌드할입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="5b7b6-114">최대값은 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b7b6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b7b6-115">Requirements</span></span>  
 <span data-ttu-id="5b7b6-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b7b6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b7b6-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b7b6-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b7b6-118">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5b7b6-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b7b6-119">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b7b6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7b6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b7b6-120">See Also</span></span>  
 [<span data-ttu-id="5b7b6-121">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="5b7b6-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
