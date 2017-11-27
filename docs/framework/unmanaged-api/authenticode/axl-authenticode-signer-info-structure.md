---
title: "AXL_AUTHENTICODE_SIGNER_INFO 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c53ca8073adda5cba497e9f45404024435cc161f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="73764-102">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="73764-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="73764-103">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73764-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73764-104">구문</span><span class="sxs-lookup"><span data-stu-id="73764-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="73764-105">멤버</span><span class="sxs-lookup"><span data-stu-id="73764-105">Members</span></span>  
  
|<span data-ttu-id="73764-106">멤버</span><span class="sxs-lookup"><span data-stu-id="73764-106">Member</span></span>|<span data-ttu-id="73764-107">설명</span><span class="sxs-lookup"><span data-stu-id="73764-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="73764-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="73764-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="73764-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="73764-111">해시입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="73764-112">설명입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="73764-113">설명의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="73764-114">서명자의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-114">The chain context of the signer.</span></span> <span data-ttu-id="73764-115">참조는 [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="73764-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73764-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73764-116">See Also</span></span>  
 [<span data-ttu-id="73764-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="73764-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
