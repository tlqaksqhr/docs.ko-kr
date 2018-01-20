---
title: "PublicKeyBlob 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1f04c692b7549c4d7d8d431591eeb867b673d9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="48fdd-102">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="48fdd-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="48fdd-103">공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48fdd-104">구문</span><span class="sxs-lookup"><span data-stu-id="48fdd-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="48fdd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="48fdd-105">Members</span></span>  
  
|<span data-ttu-id="48fdd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="48fdd-106">Member</span></span>|<span data-ttu-id="48fdd-107">설명</span><span class="sxs-lookup"><span data-stu-id="48fdd-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="48fdd-108">서명 알고리즘에 대 한 식별자 (형식의 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="48fdd-109">해시 알고리즘에 대 한 식별자 (형식의 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="48fdd-110">바이트의 키 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="48fdd-111">CryptoAPI에 의해 반환 되는 형식과의 키 값을 포함 하는 가변 길이 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48fdd-112">설명</span><span class="sxs-lookup"><span data-stu-id="48fdd-112">Remarks</span></span>  
 <span data-ttu-id="48fdd-113">`PublicKeyBlob` 구조체를 사용 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), 및를 공개/개인 키 쌍의 공개 키를 나타내는 다른 강력한 이름의 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48fdd-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48fdd-114">Requirements</span></span>  
 <span data-ttu-id="48fdd-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48fdd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48fdd-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="48fdd-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="48fdd-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="48fdd-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48fdd-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48fdd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fdd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48fdd-119">See Also</span></span>  
 [<span data-ttu-id="48fdd-120">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="48fdd-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="48fdd-121">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="48fdd-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="48fdd-122">강력한 이름 지정 구조체</span><span class="sxs-lookup"><span data-stu-id="48fdd-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
