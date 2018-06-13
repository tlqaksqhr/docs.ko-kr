---
title: 해시 코드를 사용하여 데이터 무결성 보장
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27e4abcd5e8dfe253ba8a7ea1ba5022561ed9ae7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581575"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="27733-102">해시 코드를 사용하여 데이터 무결성 보장</span><span class="sxs-lookup"><span data-stu-id="27733-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="27733-103">해시 값을 데이터를 고유하게 식별하는 고정 길이 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27733-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="27733-104">해시 값은 대용량 데이터를 훨씬 더 작은 숫자 값으로 나타내므로 디지털 서명과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27733-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="27733-105">해시 값에 서명하는 것이 더 큰 값에 서명하는 것보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="27733-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="27733-106">해시 값은 안전하지 않은 채널을 통해 전송된 데이터의 무결성을 확인하는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="27733-107">수신된 데이터의 해시 값을 전송된 데이터의 해시 값과 비교하여 데이터가 변경되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27733-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="27733-108">이 항목에서는 <xref:System.Security.Cryptography?displayProperty=nameWithType> 네임스페이스의 클래스를 사용하여 해시 코드를 생성하고 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="27733-109">해시 생성</span><span class="sxs-lookup"><span data-stu-id="27733-109">Generating a Hash</span></span>  
 <span data-ttu-id="27733-110">관리되는 해시 클래스는 바이트 배열이나 관리되는 스트림 개체를 해시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27733-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="27733-111">다음 예제에서는 SHA1 해시 알고리즘을 사용하여 문자열에 대한 해시 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27733-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="27733-112">이 예제에서는 <xref:System.Text.UnicodeEncoding> 클래스를 사용하여 문자열을 <xref:System.Security.Cryptography.SHA1Managed> 클래스를 통해 해시된 바이트 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="27733-113">해시 값이 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27733-113">The hash value is then displayed to the console.</span></span>  
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="27733-114">이 코드는 다음 문자열을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-114">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="27733-115">해시 확인</span><span class="sxs-lookup"><span data-stu-id="27733-115">Verifying a Hash</span></span>  
 <span data-ttu-id="27733-116">데이터를 해시 값과 비교하여 데이터 무결성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27733-116">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="27733-117">일반적으로 데이터는 특정 시간에 해시되고 해시 값은 몇 가지 방법으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="27733-117">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="27733-118">나중에 데이터를 다시 해시하고 보호된 값과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27733-118">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="27733-119">해시 값이 일치하면 데이터가 변경되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27733-119">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="27733-120">값이 일치하지 않으면 데이터가 손상된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27733-120">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="27733-121">이 시스템이 작동하려면 보호된 해시를 암호화하거나 모든 신뢰할 수 없는 상대방으로부터 기밀로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-121">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="27733-122">다음 예제에서는 문자열의 이전 해시 값을 새 해시 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-122">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="27733-123">이 예제에서는 해시 값의 각 바이트를 순환하고 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-123">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="27733-124">두 해시 값이 일치하면 이 코드는 다음 내용을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-124">If the two hash values match, this code displays the following to the console:</span></span>  
  
```  
The hash codes match.  
```  
  
 <span data-ttu-id="27733-125">일치하지 않으면 코드는 다음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27733-125">If they do not match, the code displays the following:</span></span>  
  
```  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="27733-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27733-126">See Also</span></span>  
 [<span data-ttu-id="27733-127">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="27733-127">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
