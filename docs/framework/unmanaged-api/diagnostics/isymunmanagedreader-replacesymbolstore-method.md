---
title: "ISymUnmanagedReader::ReplaceSymbolStore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.ReplaceSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09bcad4898cf4d3310a96164bdc82006e185006f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="1a38a-102">ISymUnmanagedReader::ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="1a38a-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="1a38a-103">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="1a38a-104">이 메서드는 비슷합니다는 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드를 제외 하 고 지정 된 델타 업데이트 보다는 완전 한 대체 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a38a-105">중 하나만 지정할 필요는 `filename` 또는 `pIStream` 두 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="1a38a-106">경우 `filename` 지정, 기호 저장소는 해당 파일에 있는 기호도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="1a38a-107">경우 `pIStream` 를 지정 된 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a38a-108">구문</span><span class="sxs-lookup"><span data-stu-id="1a38a-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a38a-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a38a-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="1a38a-110">[in] 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="1a38a-111">[in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a38a-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a38a-112">Return Value</span></span>  
 <span data-ttu-id="1a38a-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1a38a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a38a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a38a-114">Requirements</span></span>  
 <span data-ttu-id="1a38a-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a38a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a38a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a38a-116">See Also</span></span>  
 [<span data-ttu-id="1a38a-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a38a-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
