---
title: ASM_NAME 열거형
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9902b96a6f9ca56435430b6120a34dfb6cfadd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431219"
---
# <a name="asmname-enumeration"></a><span data-ttu-id="b8cc7-102">ASM_NAME 열거형</span><span class="sxs-lookup"><span data-stu-id="b8cc7-102">ASM_NAME Enumeration</span></span>
<span data-ttu-id="b8cc7-103">버전, 빌드, culture, 서명 및 어셈블리 속성을 검색 하거나 설정 하 여을 이런 식으로 나타냅니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b8cc7-103">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8cc7-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8cc7-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,   
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a><span data-ttu-id="b8cc7-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8cc7-105">Requirements</span></span>  
 <span data-ttu-id="b8cc7-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cc7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8cc7-107">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b8cc7-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b8cc7-108">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b8cc7-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8cc7-109">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8cc7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8cc7-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8cc7-110">See Also</span></span>  
 [<span data-ttu-id="b8cc7-111">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8cc7-111">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="b8cc7-112">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="b8cc7-112">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
