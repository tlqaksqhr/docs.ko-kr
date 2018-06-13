---
title: CorRefToDefCheck 열거형
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5caf432b5de7cb0c8ff0e6f53b3e79a64ecf802e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443315"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="8e11a-102">CorRefToDefCheck 열거형</span><span class="sxs-lookup"><span data-stu-id="8e11a-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="8e11a-103">코드를 최적화하기 위해 해당 정의로 변환되는 참조된 항목을 제어하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e11a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e11a-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="8e11a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8e11a-105">Members</span></span>  
  
|<span data-ttu-id="8e11a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8e11a-106">Member</span></span>|<span data-ttu-id="8e11a-107">설명</span><span class="sxs-lookup"><span data-stu-id="8e11a-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="8e11a-108">형식 참조 및 멤버 참조를 정의로 변환 되어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="8e11a-109">이 기본값 (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="8e11a-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="8e11a-110">참조 되는 모든 항목 정의로 변환 되어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="8e11a-111">참조 된 항목이 없는 정의로 변환 되어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="8e11a-112">형식 참조만 형식 정의로 변환 되어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="8e11a-113">멤버 참조만 정의로 변환 되어야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="8e11a-114">즉, 메서드 정의 또는 필드 정의를 멤버 참조를 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e11a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e11a-115">Requirements</span></span>  
 <span data-ttu-id="8e11a-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e11a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e11a-117">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8e11a-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8e11a-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e11a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e11a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e11a-119">See Also</span></span>  
 [<span data-ttu-id="8e11a-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8e11a-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
