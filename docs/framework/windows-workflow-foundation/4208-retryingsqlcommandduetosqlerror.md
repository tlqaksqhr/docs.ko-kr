---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3bfe7547fafb17503c972646d344263117d9d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="ca26b-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="ca26b-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="ca26b-103">속성</span><span class="sxs-lookup"><span data-stu-id="ca26b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca26b-104">ID</span><span class="sxs-lookup"><span data-stu-id="ca26b-104">ID</span></span>|<span data-ttu-id="ca26b-105">4208</span><span class="sxs-lookup"><span data-stu-id="ca26b-105">4208</span></span>|  
|<span data-ttu-id="ca26b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ca26b-106">Keywords</span></span>|<span data-ttu-id="ca26b-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ca26b-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ca26b-108">수준</span><span class="sxs-lookup"><span data-stu-id="ca26b-108">Level</span></span>|<span data-ttu-id="ca26b-109">정보</span><span class="sxs-lookup"><span data-stu-id="ca26b-109">Information</span></span>|  
|<span data-ttu-id="ca26b-110">채널</span><span class="sxs-lookup"><span data-stu-id="ca26b-110">Channel</span></span>|<span data-ttu-id="ca26b-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="ca26b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ca26b-112">설명</span><span class="sxs-lookup"><span data-stu-id="ca26b-112">Description</span></span>  
 <span data-ttu-id="ca26b-113">SQL 오류로 인해 SQL 공급자가 SQL 명령을 재시도하고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca26b-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ca26b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ca26b-114">Message</span></span>  
 <span data-ttu-id="ca26b-115">SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ca26b-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ca26b-116">설명</span><span class="sxs-lookup"><span data-stu-id="ca26b-116">Details</span></span>  
  
|<span data-ttu-id="ca26b-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ca26b-117">Data Item Name</span></span>|<span data-ttu-id="ca26b-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ca26b-118">Data Item Type</span></span>|<span data-ttu-id="ca26b-119">설명</span><span class="sxs-lookup"><span data-stu-id="ca26b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ca26b-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="ca26b-120">ErrorNumber</span></span>|<span data-ttu-id="ca26b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca26b-121">xs:string</span></span>|<span data-ttu-id="ca26b-122">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ca26b-122">The SQL error number.</span></span>|  
|<span data-ttu-id="ca26b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ca26b-123">AppDomain</span></span>|<span data-ttu-id="ca26b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca26b-124">xs:string</span></span>|<span data-ttu-id="ca26b-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ca26b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
