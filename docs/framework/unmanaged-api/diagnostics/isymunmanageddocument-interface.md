---
title: ISymUnmanagedDocument 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f75e517890275b90523dc42cdac3a83d871beac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427204"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="7b1f7-102">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b1f7-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="7b1f7-103">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="7b1f7-104">문서 (URL)는 uniform resource locator와 문서 형식 GUID 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="7b1f7-105">URL을 사용 하 여 저장 하는 방법에 관계 없이 문서를 찾을 수 있으며 문서 유형 GUID 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="7b1f7-106">기호 저장소에 문서 소스를 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b1f7-107">메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-107">Methods</span></span>  
  
|<span data-ttu-id="7b1f7-108">메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-108">Method</span></span>|<span data-ttu-id="7b1f7-109">설명</span><span class="sxs-lookup"><span data-stu-id="7b1f7-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b1f7-110">FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="7b1f7-111">시퀀스 포인트가 아닐 수 있는이 문서의 줄이 제공 된 시퀀스 위치가 되는 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="7b1f7-112">GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="7b1f7-113">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="7b1f7-114">GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="7b1f7-115">체크섬이 없는 경우에 모두 0으로 GUID를 반환 하거나 체크섬 알고리즘 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="7b1f7-116">GetDocumentType 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="7b1f7-117">이 문서의 문서 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="7b1f7-118">GetLanguage 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="7b1f7-119">이 문서의 언어 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="7b1f7-120">GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="7b1f7-121">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="7b1f7-122">GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="7b1f7-123">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="7b1f7-124">GetSourceRange 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="7b1f7-125">지정 된 버퍼로 포함된 리소스의 지정된 된 범위를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="7b1f7-126">GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="7b1f7-127">이 문서에 대 한 URL을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="7b1f7-128">HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="7b1f7-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="7b1f7-129">반환 `true` 문서 소스 디버깅 기호;에 대해 포함 된 경우는 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1f7-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b1f7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b1f7-130">See Also</span></span>  
 [<span data-ttu-id="7b1f7-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b1f7-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
