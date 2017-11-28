---
title: "AddFile2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddFile2
- IALink2.AddFile2
api_location: alink.dll
api_type: COM
f1_keywords: AddFile2
helpviewer_keywords: AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe10a3ca8930087a52d02905534696dbb2d8fb25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="addfile2-method"></a><span data-ttu-id="44873-102">AddFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="44873-102">AddFile2 Method</span></span>
<span data-ttu-id="44873-103">어셈블리에 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-103">Adds files to the assembly.</span></span> <span data-ttu-id="44873-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44873-105">구문</span><span class="sxs-lookup"><span data-stu-id="44873-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44873-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44873-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="44873-107">파일이 추가 되는 어셈블리에 대 한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="44873-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="44873-108">추가할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44873-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="44873-109">COM + `FileDef` 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="44873-110">`dwFlags`에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="44873-111">인터페이스를 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="44873-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="44873-112">추가 중인 파일에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="44873-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44873-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="44873-113">Return Value</span></span>  
 <span data-ttu-id="44873-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44873-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44873-115">Requirements</span></span>  
 <span data-ttu-id="44873-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="44873-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44873-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44873-117">See Also</span></span>  
 [<span data-ttu-id="44873-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44873-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="44873-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44873-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="44873-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="44873-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
