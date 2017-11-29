---
title: "CorRegFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRegFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRegFlags
helpviewer_keywords: CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8118de9f4fc6a4f2820b88685b9b87c498328b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="c9bc9-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="c9bc9-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="c9bc9-103">모듈 또는 합성 이미지를 설치할 때 등록에 사용 되는 플래그 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc9-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9bc9-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c9bc9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c9bc9-105">Members</span></span>  
  
|<span data-ttu-id="c9bc9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c9bc9-106">Member</span></span>|<span data-ttu-id="c9bc9-107">설명</span><span class="sxs-lookup"><span data-stu-id="c9bc9-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="c9bc9-108">파일 대상에 복사 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc9-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="c9bc9-109">모듈 또는 합성 이미지는 구성의 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc9-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="c9bc9-110">모듈 또는 합성 클래스 참조에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc9-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9bc9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9bc9-111">Requirements</span></span>  
 <span data-ttu-id="c9bc9-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bc9-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c9bc9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9bc9-114">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c9bc9-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9bc9-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bc9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bc9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9bc9-116">See Also</span></span>  
 [<span data-ttu-id="c9bc9-117">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c9bc9-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
