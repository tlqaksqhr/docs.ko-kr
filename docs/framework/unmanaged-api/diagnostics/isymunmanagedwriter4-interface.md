---
title: "ISymUnmanagedWriter4 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5531b491da70cb78de1234e750c2e15390c10ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="61a69-102">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61a69-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="61a69-103">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="61a69-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a69-104">구문</span><span class="sxs-lookup"><span data-stu-id="61a69-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="61a69-105">메서드</span><span class="sxs-lookup"><span data-stu-id="61a69-105">Methods</span></span>  
 <span data-ttu-id="61a69-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a69-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="61a69-107">메서드</span><span class="sxs-lookup"><span data-stu-id="61a69-107">Method</span></span>|<span data-ttu-id="61a69-108">설명</span><span class="sxs-lookup"><span data-stu-id="61a69-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61a69-109">GetDebugInfoWithPadding 메서드</span><span class="sxs-lookup"><span data-stu-id="61a69-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="61a69-110">동일 하 게 작동 [GetDebugInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) 제외 하 고 경로 문자열을 문자열 데이터의 크기가 고정 되어 null 종결 문자 뒤에 오는 0으로 채워서 `MAX_PATH`합니다.</span><span class="sxs-lookup"><span data-stu-id="61a69-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="61a69-111">경로 문자열 길이 자체 경우 안쪽 여백을 지정 되어 보다 작은 `MAX_PATH`합니다.</span><span class="sxs-lookup"><span data-stu-id="61a69-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="61a69-112">이렇게 하면 더 쉽게 차이 PE 파일에 해당 도구를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a69-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61a69-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61a69-113">Requirements</span></span>  
 <span data-ttu-id="61a69-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61a69-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a69-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61a69-115">See Also</span></span>  
 [<span data-ttu-id="61a69-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61a69-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="61a69-117">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61a69-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
