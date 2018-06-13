---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 103444e0b4b17b6384473eac714fba025cee9a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426544"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="4b355-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="4b355-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="4b355-103">기호 검색 정보의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b355-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b355-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b355-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b355-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b355-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="4b355-106">out]]에 대 한 포인터는 `ULONG32` 검색 정보를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b355-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b355-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4b355-107">Return Value</span></span>  
 <span data-ttu-id="4b355-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b355-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b355-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b355-109">Requirements</span></span>  
 <span data-ttu-id="4b355-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4b355-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b355-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b355-111">See Also</span></span>  
 [<span data-ttu-id="4b355-112">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b355-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
