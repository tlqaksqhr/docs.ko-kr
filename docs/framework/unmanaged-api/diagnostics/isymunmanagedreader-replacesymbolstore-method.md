---
title: ISymUnmanagedReader::ReplaceSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03607cf96d73e96eef63fe62b86b50be02f34421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428204"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="286d4-102">ISymUnmanagedReader::ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="286d4-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="286d4-103">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="286d4-104">이 메서드는 비슷합니다는 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드를 제외 하 고 지정 된 델타 업데이트 보다는 완전 한 대체 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="286d4-105">중 하나만 지정할 필요는 `filename` 또는 `pIStream` 두 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="286d4-106">경우 `filename` 지정, 기호 저장소는 해당 파일에 있는 기호도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="286d4-107">경우 `pIStream` 를 지정 된 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286d4-108">구문</span><span class="sxs-lookup"><span data-stu-id="286d4-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="286d4-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="286d4-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="286d4-110">[in] 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="286d4-111">[in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="286d4-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="286d4-112">Return Value</span></span>  
 <span data-ttu-id="286d4-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="286d4-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="286d4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="286d4-114">Requirements</span></span>  
 <span data-ttu-id="286d4-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="286d4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286d4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="286d4-116">See Also</span></span>  
 [<span data-ttu-id="286d4-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="286d4-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
