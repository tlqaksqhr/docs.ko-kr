---
title: ISymUnmanagedDocument::GetLanguageVendor 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a6830f47d5cac2cf9c84144c18486489b0ec581
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424533"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="a7901-102">ISymUnmanagedDocument::GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="a7901-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="a7901-103">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7901-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7901-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7901-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7901-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7901-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a7901-106">[out] 언어 공급 업체를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7901-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7901-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7901-107">Return Value</span></span>  
 <span data-ttu-id="a7901-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="a7901-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7901-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7901-109">See Also</span></span>  
 [<span data-ttu-id="a7901-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7901-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
