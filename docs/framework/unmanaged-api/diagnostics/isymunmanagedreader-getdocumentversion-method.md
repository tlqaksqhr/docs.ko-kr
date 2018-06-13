---
title: ISymUnmanagedReader::GetDocumentVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31b550c7b3cec999b0420fbdc06582a24f420abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425986"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="c1cff-102">ISymUnmanagedReader::GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="c1cff-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="c1cff-103">지정 된 문서의 지정된 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="c1cff-104">문서 버전 1에서 시작 하 고 문서를 사용 하 여이 업데이트 될 때마다 증가 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c1cff-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="c1cff-105">경우는 `pbCurrent` 매개 변수는 `true`, 문서의 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1cff-106">구문</span><span class="sxs-lookup"><span data-stu-id="c1cff-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1cff-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1cff-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="c1cff-108">[in] 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="c1cff-109">[out] 지정된 된 문서 버전을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="c1cff-110">[out] 수신 하는 변수에 대 한 포인터 `true` 최신 버전의 문서, 이것이 또는 `false` 그렇지 않으면 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1cff-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c1cff-111">Return Value</span></span>  
 <span data-ttu-id="c1cff-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1cff-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1cff-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1cff-113">Requirements</span></span>  
 <span data-ttu-id="c1cff-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c1cff-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cff-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1cff-115">See Also</span></span>  
 [<span data-ttu-id="c1cff-116">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1cff-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
