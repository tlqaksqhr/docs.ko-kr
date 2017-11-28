---
title: "ImportTypes2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportTypes2
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes2
helpviewer_keywords: ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d707cdd827b5e435c961a14e67170ab0e2bc90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes2-method"></a><span data-ttu-id="9a1bb-102">ImportTypes2 메서드</span><span class="sxs-lookup"><span data-stu-id="9a1bb-102">ImportTypes2 Method</span></span>
<span data-ttu-id="9a1bb-103">형식 가져오기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-103">Initiates the import of types.</span></span> <span data-ttu-id="9a1bb-104">형식을 통해 가져온 각 범위에서 가져오기를 시작 하려면이 메서드를 호출 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="9a1bb-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a1bb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a1bb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9a1bb-107">가져올 대상 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9a1bb-108">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9a1bb-109">가져올 0부터 시작 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="9a1bb-110">지정된 된 범위에서의 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9a1bb-111">필요에 따라 받는 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="9a1bb-112">필요에 따라 지정된 된 범위에서 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a1bb-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="9a1bb-113">Return Value</span></span>  
 <span data-ttu-id="9a1bb-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1bb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a1bb-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a1bb-115">Requirements</span></span>  
 <span data-ttu-id="9a1bb-116">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="9a1bb-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1bb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a1bb-117">See Also</span></span>  
 [<span data-ttu-id="9a1bb-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a1bb-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9a1bb-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a1bb-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9a1bb-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="9a1bb-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
