---
title: ISymUnmanagedReader::UpdateSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81f9db872e9904d2297221e266be710837d0fb66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427384"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="027dd-102">ISymUnmanagedReader::UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="027dd-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="027dd-103">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="027dd-104">이 메서드는 델타 원래 이식 가능한 실행 (PE) 파일에 맞게 기호 저장소를 업데이트 하려면 편집 하며 계속 하기 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="027dd-105">중 하나만 지정할 필요는 `filename` 또는 `pIStream` 두 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="027dd-106">경우 `filename` 지정, 기호 저장소는 해당 파일에 있는 기호도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="027dd-107">경우 `pIStream` 를 지정 된 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027dd-108">구문</span><span class="sxs-lookup"><span data-stu-id="027dd-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="027dd-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="027dd-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="027dd-110">[in] 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="027dd-111">[in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="027dd-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="027dd-112">Return Value</span></span>  
 <span data-ttu-id="027dd-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="027dd-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="027dd-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="027dd-114">Requirements</span></span>  
 <span data-ttu-id="027dd-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="027dd-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027dd-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="027dd-116">See Also</span></span>  
 [<span data-ttu-id="027dd-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="027dd-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
