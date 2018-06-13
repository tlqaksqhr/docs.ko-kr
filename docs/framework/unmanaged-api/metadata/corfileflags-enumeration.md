---
title: CorFileFlags 열거형
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ecc2f62a6bb8119b7fe06a82aea827a58d04ecb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441670"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="09450-102">CorFileFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="09450-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="09450-103">에 대 한 호출에 정의 된 파일의 형식을 설명 하는 값이 포함 되어 [imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09450-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09450-104">구문</span><span class="sxs-lookup"><span data-stu-id="09450-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="09450-105">멤버</span><span class="sxs-lookup"><span data-stu-id="09450-105">Members</span></span>  
  
|<span data-ttu-id="09450-106">멤버</span><span class="sxs-lookup"><span data-stu-id="09450-106">Member</span></span>|<span data-ttu-id="09450-107">설명</span><span class="sxs-lookup"><span data-stu-id="09450-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="09450-108">파일 리소스 파일 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09450-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="09450-109">리소스 파일 수 파일 메타 데이터가 포함 되지 않습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09450-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09450-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09450-110">Requirements</span></span>  
 <span data-ttu-id="09450-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09450-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09450-112">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="09450-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="09450-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09450-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09450-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09450-114">See Also</span></span>  
 [<span data-ttu-id="09450-115">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="09450-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
