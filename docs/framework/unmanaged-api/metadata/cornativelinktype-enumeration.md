---
title: CorNativeLinkType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bf8848851dc99c60b8c151ed34cd536fa9a8fed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443263"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="13a6a-102">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="13a6a-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="13a6a-103">네이티브 코드에서 연결된 형식을 나타내는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="13a6a-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="13a6a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="13a6a-105">Members</span></span>  
  
|<span data-ttu-id="13a6a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="13a6a-106">Member</span></span>|<span data-ttu-id="13a6a-107">설명</span><span class="sxs-lookup"><span data-stu-id="13a6a-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="13a6a-108">지정 된 키워드가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="13a6a-109">ANSI 키워드가 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="13a6a-110">유니코드 키워드가 지정 되어 있는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="13a6a-111">Auto 키워드 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="13a6a-112">OLE 키워드가 지정 되어 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="13a6a-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13a6a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13a6a-114">Requirements</span></span>  
 <span data-ttu-id="13a6a-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="13a6a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a6a-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13a6a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13a6a-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="13a6a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13a6a-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a6a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a6a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13a6a-119">See Also</span></span>  
 [<span data-ttu-id="13a6a-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="13a6a-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
