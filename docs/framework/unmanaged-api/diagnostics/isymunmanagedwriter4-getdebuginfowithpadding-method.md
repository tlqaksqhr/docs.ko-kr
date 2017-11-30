---
title: "ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f2f0aad37fcd63e2345cd32a00b44412ed8c7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="b6e77-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드</span><span class="sxs-lookup"><span data-stu-id="b6e77-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="b6e77-103">동일 하 게 작동 [GetDebugInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) 제외 하 고 경로 문자열을 문자열 데이터의 크기가 고정 되어 null 종결 문자 뒤에 오는 0으로 채워서 `MAX_PATH`합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e77-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="b6e77-104">경로 문자열 길이 자체 경우 안쪽 여백을 지정 되어 보다 작은 `MAX_PATH`합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e77-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="b6e77-105">이렇게 하면 더 쉽게 차이 PE 파일에 해당 도구를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e77-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e77-106">구문</span><span class="sxs-lookup"><span data-stu-id="b6e77-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6e77-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6e77-107">Parameters</span></span>  
  
|<span data-ttu-id="b6e77-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6e77-108">Parameter</span></span>|<span data-ttu-id="b6e77-109">설명</span><span class="sxs-lookup"><span data-stu-id="b6e77-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="b6e77-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b6e77-110">Return Value</span></span>  
 <span data-ttu-id="b6e77-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e77-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e77-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6e77-112">Requirements</span></span>  
 <span data-ttu-id="b6e77-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6e77-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e77-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6e77-114">See Also</span></span>  
 [<span data-ttu-id="b6e77-115">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6e77-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
