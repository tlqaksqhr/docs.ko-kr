---
title: AXL_AUTHENTICODE_SIGNER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400447"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="f8b01-102">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="f8b01-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="f8b01-103">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b01-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8b01-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f8b01-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f8b01-105">Members</span></span>  
  
|<span data-ttu-id="f8b01-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f8b01-106">Member</span></span>|<span data-ttu-id="f8b01-107">설명</span><span class="sxs-lookup"><span data-stu-id="f8b01-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="f8b01-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="f8b01-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="f8b01-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="f8b01-111">해시입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="f8b01-112">설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="f8b01-113">설명의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="f8b01-114">서명자의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-114">The chain context of the signer.</span></span> <span data-ttu-id="f8b01-115">참조는 [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b01-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8b01-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8b01-116">See Also</span></span>  
 [<span data-ttu-id="f8b01-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f8b01-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
