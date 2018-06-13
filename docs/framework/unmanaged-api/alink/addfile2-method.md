---
title: AddFile2 메서드
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4735103f277d710dd23adfa19c475c425feaa36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403333"
---
# <a name="addfile2-method"></a><span data-ttu-id="a69bb-102">AddFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="a69bb-102">AddFile2 Method</span></span>
<span data-ttu-id="a69bb-103">어셈블리에 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-103">Adds files to the assembly.</span></span> <span data-ttu-id="a69bb-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="a69bb-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a69bb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a69bb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a69bb-107">파일이 추가 되는 어셈블리에 대 한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="a69bb-108">추가할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a69bb-109">COM + `FileDef` 플래그와 같은 `ffContainsNoMetaData` 및 `ffWriteable`합니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="a69bb-110">`dwFlags` 에 전달 [DefineFile 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="a69bb-111">인터페이스를 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="a69bb-112">추가 중인 파일에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a69bb-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="a69bb-113">Return Value</span></span>  
 <span data-ttu-id="a69bb-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a69bb-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a69bb-115">Requirements</span></span>  
 <span data-ttu-id="a69bb-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a69bb-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69bb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a69bb-117">See Also</span></span>  
 [<span data-ttu-id="a69bb-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a69bb-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a69bb-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a69bb-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a69bb-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="a69bb-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
