---
title: "CorFileFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFileFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFileFlags
helpviewer_keywords: CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf123f734f73ecfe726a80099de6ec06b0ced06b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="5e77a-102">CorFileFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="5e77a-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="5e77a-103">에 대 한 호출에 정의 된 파일의 형식을 설명 하는 값이 포함 되어 [imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e77a-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e77a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e77a-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5e77a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5e77a-105">Members</span></span>  
  
|<span data-ttu-id="5e77a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5e77a-106">Member</span></span>|<span data-ttu-id="5e77a-107">설명</span><span class="sxs-lookup"><span data-stu-id="5e77a-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="5e77a-108">파일 리소스 파일 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e77a-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="5e77a-109">리소스 파일 수 파일 메타 데이터가 포함 되지 않습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e77a-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e77a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e77a-110">Requirements</span></span>  
 <span data-ttu-id="5e77a-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e77a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e77a-112">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5e77a-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5e77a-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e77a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e77a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e77a-114">See Also</span></span>  
 [<span data-ttu-id="5e77a-115">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="5e77a-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
