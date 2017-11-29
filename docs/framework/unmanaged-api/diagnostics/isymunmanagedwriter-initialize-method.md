---
title: "ISymUnmanagedWriter::Initialize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="cf10f-102">ISymUnmanagedWriter::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="cf10f-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="cf10f-103">이 작성기를 연결, 될 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 기록할 출력 파일 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="cf10f-104">이 메서드를 한 번만 호출할 수 있습니다 및 다른 기록기 메서드보다 먼저 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="cf10f-105">일부 작성기에는 파일 이름이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-105">Some writers may require a file name.</span></span> <span data-ttu-id="cf10f-106">그러나이 메서드에 파일 이름을 사용 하지 않는 작성기에 나쁜 영향 없이 항상 파일 이름을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf10f-107">구문</span><span class="sxs-lookup"><span data-stu-id="cf10f-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf10f-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf10f-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="cf10f-109">[in] 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="cf10f-110">[in] 에 디버깅 기호가 쓰여진 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="cf10f-111">파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="cf10f-112">[in] 기호 작성기를 지정 하는 경우에 대 한 기호를 내보냅니다는 주어진 <xref:System.Runtime.InteropServices.ComTypes.IStream> 대신에 지정 된 파일에는 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="cf10f-113">`pIStream` 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="cf10f-114">[in] `true` 이것이 전체를 다시 빌드해야 합니다. `false` 증분 컴파일을 이것이 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf10f-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="cf10f-115">Return Value</span></span>  
 <span data-ttu-id="cf10f-116">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cf10f-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf10f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf10f-117">Requirements</span></span>  
 <span data-ttu-id="cf10f-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cf10f-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf10f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf10f-119">See Also</span></span>  
 [<span data-ttu-id="cf10f-120">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf10f-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="cf10f-121">Initialize2 메서드</span><span class="sxs-lookup"><span data-stu-id="cf10f-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
