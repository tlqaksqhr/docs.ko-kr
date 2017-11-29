---
title: "ImportFileEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71a7bc1ba9f23f1c581ca3528752e04003d9857c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="5c894-102">ImportFileEx 메서드</span><span class="sxs-lookup"><span data-stu-id="5c894-102">ImportFileEx Method</span></span>
<span data-ttu-id="5c894-103">표시 된 어셈블리 또는 바인딩되지 않은 모듈을 가져오기.</span><span class="sxs-lookup"><span data-stu-id="5c894-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c894-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c894-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c894-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c894-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5c894-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5c894-107">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5c894-108">True 이면 ImportTypes 사용 되는, 그렇지 않으면 가져올 수 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5c894-109">에 전달 하는 플래그를 [OpenScope 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5c894-110">가져올 파일의 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5c894-111">받을 어셈블리 가져오기 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5c894-112">파일 어셈블리가 아닌 경우 NULL로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5c894-113">가져온된 파일 및/또는 범위의 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c894-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="5c894-114">Return Value</span></span>  
 <span data-ttu-id="5c894-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c894-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c894-116">Requirements</span></span>  
 <span data-ttu-id="5c894-117">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c894-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c894-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c894-118">See Also</span></span>  
 [<span data-ttu-id="5c894-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c894-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5c894-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c894-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5c894-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="5c894-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
