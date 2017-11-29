---
title: "ImportFile2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile2
helpviewer_keywords: ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4d7e842152e84992124ec29cd551c3b5d50a6d61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="importfile2-method"></a><span data-ttu-id="eecef-102">ImportFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="eecef-102">ImportFile2 Method</span></span>
<span data-ttu-id="eecef-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="eecef-104">이 방법은 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 하지만 가져오는 파일이 디스크에 존재 하지 않는 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eecef-105">구문</span><span class="sxs-lookup"><span data-stu-id="eecef-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eecef-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eecef-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="eecef-107">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="eecef-108">어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="eecef-109">선택적 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="eecef-110">True 이면 ImportTypes 사용 되는, 그렇지 않으면 가져올 수 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="eecef-111">파일 또는 어셈블리에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="eecef-112">수신 된 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="eecef-113">파일 어셈블리가 아닌 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="eecef-114">파일 및/또는 가져온 범위 발견 된 빌드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eecef-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="eecef-115">Return Value</span></span>  
 <span data-ttu-id="eecef-116">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eecef-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eecef-117">Requirements</span></span>  
 <span data-ttu-id="eecef-118">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eecef-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eecef-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eecef-119">See Also</span></span>  
 [<span data-ttu-id="eecef-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eecef-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="eecef-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eecef-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="eecef-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="eecef-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
