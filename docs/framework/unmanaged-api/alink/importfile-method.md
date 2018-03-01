---
title: "ImportFile 메서드"
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
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5d4f93336fe19210086c39b8db6d167b3caa222
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="importfile-method"></a><span data-ttu-id="c2fb7-102">ImportFile 메서드</span><span class="sxs-lookup"><span data-stu-id="c2fb7-102">ImportFile Method</span></span>
<span data-ttu-id="c2fb7-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2fb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2fb7-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2fb7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2fb7-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="c2fb7-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="c2fb7-107">어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="c2fb7-108">True 이면 ImportTypes 사용 되는, 그렇지 않으면 가져올 수 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="c2fb7-109">고유한 파일 ID를 저장할 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="c2fb7-110">파일은 어셈블리 또는 파일 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="c2fb7-111">포인터를 받는 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="c2fb7-112">파일 어셈블리가 아닌 경우 NULL이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="c2fb7-113">파일 및/또는 가져온 범위 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2fb7-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="c2fb7-114">Return Value</span></span>  
 <span data-ttu-id="c2fb7-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2fb7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2fb7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2fb7-116">Requirements</span></span>  
 <span data-ttu-id="c2fb7-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="c2fb7-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fb7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2fb7-118">See Also</span></span>  
 [<span data-ttu-id="c2fb7-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2fb7-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c2fb7-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2fb7-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c2fb7-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="c2fb7-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
