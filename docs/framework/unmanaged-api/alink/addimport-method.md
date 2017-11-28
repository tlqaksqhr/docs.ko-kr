---
title: AddImport Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd0e55cab6f0fdb7f971d7cf06e5703340e32307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="1256c-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="1256c-102">AddImport Method1</span></span>
<span data-ttu-id="1256c-103">Imports 어셈블리에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1256c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1256c-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1256c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1256c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1256c-106">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="1256c-107">검색 된 고유 ID [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1256c-108">COM + FileDef 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="1256c-109">`dwFlags`에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="1256c-110">결과 파일에 대 한 ID를 받는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1256c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="1256c-111">Return Value</span></span>  
 <span data-ttu-id="1256c-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1256c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1256c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1256c-113">Requirements</span></span>  
 <span data-ttu-id="1256c-114">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="1256c-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1256c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1256c-115">See Also</span></span>  
 [<span data-ttu-id="1256c-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1256c-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1256c-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1256c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1256c-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="1256c-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
