---
title: "GetFileDef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 473cbaba8712ee247733ba3075c0163e259cf4dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="ab1fa-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="ab1fa-102">GetFileDef Method</span></span>
<span data-ttu-id="ab1fa-103">(반대로 ALink에서 할당 된 토큰) 메타 데이터에 사용 되는 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fa-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1fa-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab1fa-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab1fa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab1fa-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ab1fa-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fa-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="ab1fa-107">토큰 추가 된 파일의 AddFile 메서드 또는 AddImport 메서드에서 검색 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fa-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="ab1fa-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fa-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab1fa-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab1fa-109">Return Value</span></span>  
 <span data-ttu-id="ab1fa-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1fa-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1fa-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab1fa-111">Requirements</span></span>  
 <span data-ttu-id="ab1fa-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="ab1fa-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1fa-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab1fa-113">See Also</span></span>  
 [<span data-ttu-id="ab1fa-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab1fa-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ab1fa-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab1fa-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ab1fa-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="ab1fa-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
