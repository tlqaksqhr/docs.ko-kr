---
title: '끝점: Security Validation and Authentication Failures'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8c46354fac11f5f0b46ef1b5629157f6da455fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471809"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="5280f-102">끝점: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="5280f-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="5280f-103">카운터 이름: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="5280f-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="5280f-104">설명</span><span class="sxs-lookup"><span data-stu-id="5280f-104">Description</span></span>  
 <span data-ttu-id="5280f-105">이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="5280f-106">이러한 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="5280f-107">클라이언트 토큰을 메시지에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="5280f-108">클라이언트 토큰에서 인증에 실패했습니다(잘못된 암호).</span><span class="sxs-lookup"><span data-stu-id="5280f-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="5280f-109">서명 확인에 실패했습니다(메시지 변조).</span><span class="sxs-lookup"><span data-stu-id="5280f-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="5280f-110">메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="5280f-111">해독 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="5280f-112">일부 필수 요소(타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="5280f-113">TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5280f-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
