---
title: "서비스: Security Validation and Authentication Failures"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 808c0d648043df6c5a3dda4646e45ba1492345a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="ab1ea-102">서비스: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="ab1ea-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="ab1ea-103">카운터 이름: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="ab1ea-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="ab1ea-104">설명</span><span class="sxs-lookup"><span data-stu-id="ab1ea-104">Description</span></span>  
 <span data-ttu-id="ab1ea-105">이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="ab1ea-106">이러한 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="ab1ea-107">클라이언트 토큰을 메시지에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="ab1ea-108">클라이언트 토큰에서 인증에 실패했습니다(예: 잘못된 암호).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="ab1ea-109">서명 확인에 실패했습니다(예: 메시지 변조).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="ab1ea-110">메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="ab1ea-111">해독 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="ab1ea-112">일부 필수 요소(예: 타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="ab1ea-113">TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
