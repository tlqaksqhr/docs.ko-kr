---
title: ISymUnmanagedWriter::DefineDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 532f69afd949971fbb4f56a8fdbcc6eab159446f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427709"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="679a5-102">ISymUnmanagedWriter::DefineDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="679a5-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="679a5-103">소스 문서를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-103">Defines a source document.</span></span> <span data-ttu-id="679a5-104">Guid는 알려진된 언어, 공급 업체 및 문서 형식을 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="679a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="679a5-105">Syntax</span></span>  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="679a5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="679a5-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="679a5-107">[in] 에 대 한 포인터는 `WCHAR` 문서를 식별 하는 uniform resource locator (URL)을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="679a5-108">[in] 문서 언어를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="679a5-109">[in] 문서 언어의 공급 업체의 id를 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="679a5-110">[in] 문서의 유형을 정의 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="679a5-111">[out] 반환 된에 대 한 포인터 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="679a5-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="679a5-112">Return Value</span></span>  
 <span data-ttu-id="679a5-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="679a5-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="679a5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="679a5-114">Requirements</span></span>  
 <span data-ttu-id="679a5-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="679a5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679a5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="679a5-116">See Also</span></span>  
 [<span data-ttu-id="679a5-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="679a5-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
