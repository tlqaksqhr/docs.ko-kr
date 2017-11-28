---
title: "ImportTypes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="2e3a1-102">ImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="2e3a1-102">ImportTypes Method</span></span>
<span data-ttu-id="2e3a1-103">형식을 통해 가져온 각 범위에서 가져오기를 시작 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e3a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e3a1-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e3a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e3a1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2e3a1-106">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2e3a1-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="2e3a1-108">가져올 범위 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="2e3a1-109">이 범위에는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="2e3a1-110">필요에 따라 받는 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="2e3a1-111">필요에 따라 표시 된 범위의 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e3a1-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="2e3a1-112">Return Value</span></span>  
 <span data-ttu-id="2e3a1-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e3a1-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e3a1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e3a1-114">Requirements</span></span>  
 <span data-ttu-id="2e3a1-115">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="2e3a1-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3a1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e3a1-116">See Also</span></span>  
 [<span data-ttu-id="2e3a1-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e3a1-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="2e3a1-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e3a1-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="2e3a1-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="2e3a1-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
