---
title: "ISymUnmanagedReader::Initialize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5917fbe3cebe9b1e9ab91d113aee2461f414c14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="59042-102">ISymUnmanagedReader::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="59042-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="59042-103">이 판독기가 되는 모듈의 파일 이름과 함께 연결 된 메타 데이터 가져오기 인터페이스의 기호 판독기를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="59042-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59042-104">이 메서드를 한 번만 호출할 수 있습니다 및 다른 판독기 메서드보다 먼저 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59042-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59042-105">구문</span><span class="sxs-lookup"><span data-stu-id="59042-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59042-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59042-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="59042-107">[in] 이 판독기를 연결 되는 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="59042-108">[in] 모듈의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-108">[in] The file name of the module.</span></span> <span data-ttu-id="59042-109">사용할 수는 `pIStream` 매개 변수 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="59042-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="59042-110">[in] 검색할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-110">[in] The path to search.</span></span> <span data-ttu-id="59042-111">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="59042-112">[in] Filename 매개 변수를 대신 사용 되는 파일 스트림.</span><span class="sxs-lookup"><span data-stu-id="59042-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59042-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="59042-113">Return Value</span></span>  
 <span data-ttu-id="59042-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59042-115">설명</span><span class="sxs-lookup"><span data-stu-id="59042-115">Remarks</span></span>  
 <span data-ttu-id="59042-116">중 하나만 지정 하는 `filename` 또는 `pIStream` 매개 변수를 둘 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="59042-117">`searchPath` 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="59042-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59042-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59042-118">Requirements</span></span>  
 <span data-ttu-id="59042-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="59042-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59042-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59042-120">See Also</span></span>  
 [<span data-ttu-id="59042-121">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59042-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
