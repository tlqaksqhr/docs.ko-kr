---
title: "GetFileDef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetFileDef
api_location: alink.dll
api_type: COM
f1_keywords: GetFileDef
helpviewer_keywords: GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a31dee6bb1af4f555211822a3b7ec108353214a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="a7f8c-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="a7f8c-102">GetFileDef Method</span></span>
<span data-ttu-id="a7f8c-103">(반대로 ALink에서 할당 된 토큰) 메타 데이터에 사용 되는 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f8c-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7f8c-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7f8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7f8c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a7f8c-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f8c-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="a7f8c-107">토큰 추가 된 파일의 AddFile 메서드 또는 AddImport 메서드에서 검색 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f8c-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="a7f8c-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f8c-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7f8c-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7f8c-109">Return Value</span></span>  
 <span data-ttu-id="a7f8c-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f8c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7f8c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7f8c-111">Requirements</span></span>  
 <span data-ttu-id="a7f8c-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="a7f8c-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f8c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7f8c-113">See Also</span></span>  
 [<span data-ttu-id="a7f8c-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7f8c-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a7f8c-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7f8c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a7f8c-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="a7f8c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
