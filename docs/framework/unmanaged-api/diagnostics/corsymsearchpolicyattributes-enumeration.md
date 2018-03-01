---
title: "CorSymSearchPolicyAttributes 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc1bef8c393a7778c194b2d4d45c3abdb583fecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="a5dfc-102">CorSymSearchPolicyAttributes 열거형</span><span class="sxs-lookup"><span data-stu-id="a5dfc-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="a5dfc-103">기호 판독기에 대 한 검색을 수행할 때 사용할 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="a5dfc-104">이러한 상수는에서 사용 되는 [isymunmanagedbinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) 및 [isymunmanagedbinder3:: Getreaderfromcallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5dfc-105">것은 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안상 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dfc-106">구문</span><span class="sxs-lookup"><span data-stu-id="a5dfc-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="a5dfc-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a5dfc-107">Members</span></span>  
  
|<span data-ttu-id="a5dfc-108">멤버</span><span class="sxs-lookup"><span data-stu-id="a5dfc-108">Member</span></span>|<span data-ttu-id="a5dfc-109">설명</span><span class="sxs-lookup"><span data-stu-id="a5dfc-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="a5dfc-110">기호 검색 경로 대 한 레지스트리를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="a5dfc-111">기호 서버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="a5dfc-112">디버그 디렉터리에 지정 된 경로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="a5dfc-113">.Exe 파일이 있는 위치에 있는 PDB 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5dfc-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5dfc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5dfc-114">Requirements</span></span>  
 <span data-ttu-id="a5dfc-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5dfc-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dfc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5dfc-116">See Also</span></span>  
 [<span data-ttu-id="a5dfc-117">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="a5dfc-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
