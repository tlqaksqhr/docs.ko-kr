---
title: ImportFileEx2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be6332c76b3dae9c02e1a939286b70438ee14cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400681"
---
# <a name="importfileex2-method"></a><span data-ttu-id="32ede-102">ImportFileEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="32ede-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="32ede-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="32ede-104">이 방법은 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 하지만 가져오는 파일이 디스크에 존재 하지 않는 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32ede-105">구문</span><span class="sxs-lookup"><span data-stu-id="32ede-105">Syntax</span></span>  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32ede-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32ede-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="32ede-107">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="32ede-108">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="32ede-109">선택적 가져오기 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="32ede-110">True 이면 ImportTypes 사용 되는, 그렇지 않으면 가져올 수 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="32ede-111">에 전달 하는 플래그를 [OpenScope 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="32ede-112">어셈블리 또는 파일에 대 한 고유 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="32ede-113">받을 어셈블리 가져오기 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="32ede-114">파일 어셈블리가 아닌 경우 NULL이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="32ede-115">파일 및/또는 가져온 범위 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32ede-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="32ede-116">Return Value</span></span>  
 <span data-ttu-id="32ede-117">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32ede-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32ede-118">Requirements</span></span>  
 <span data-ttu-id="32ede-119">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="32ede-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ede-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32ede-120">See Also</span></span>  
 [<span data-ttu-id="32ede-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32ede-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="32ede-122">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32ede-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="32ede-123">ALink API</span><span class="sxs-lookup"><span data-stu-id="32ede-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
