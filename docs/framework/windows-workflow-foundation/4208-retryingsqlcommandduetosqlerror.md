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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01db76802b96bd32e8a01cf86b1e682defe97a06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="af832-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="af832-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="af832-103">속성</span><span class="sxs-lookup"><span data-stu-id="af832-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af832-104">ID</span><span class="sxs-lookup"><span data-stu-id="af832-104">ID</span></span>|<span data-ttu-id="af832-105">4208</span><span class="sxs-lookup"><span data-stu-id="af832-105">4208</span></span>|  
|<span data-ttu-id="af832-106">키워드</span><span class="sxs-lookup"><span data-stu-id="af832-106">Keywords</span></span>|<span data-ttu-id="af832-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="af832-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="af832-108">수준</span><span class="sxs-lookup"><span data-stu-id="af832-108">Level</span></span>|<span data-ttu-id="af832-109">정보</span><span class="sxs-lookup"><span data-stu-id="af832-109">Information</span></span>|  
|<span data-ttu-id="af832-110">채널</span><span class="sxs-lookup"><span data-stu-id="af832-110">Channel</span></span>|<span data-ttu-id="af832-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="af832-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="af832-112">설명</span><span class="sxs-lookup"><span data-stu-id="af832-112">Description</span></span>  
 <span data-ttu-id="af832-113">SQL 오류로 인해 SQL 공급자가 SQL 명령을 재시도하고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af832-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="af832-114">메시지</span><span class="sxs-lookup"><span data-stu-id="af832-114">Message</span></span>  
 <span data-ttu-id="af832-115">SQL 오류 %1번으로 인해 SQL 명령을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="af832-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="af832-116">설명</span><span class="sxs-lookup"><span data-stu-id="af832-116">Details</span></span>  
  
|<span data-ttu-id="af832-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="af832-117">Data Item Name</span></span>|<span data-ttu-id="af832-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="af832-118">Data Item Type</span></span>|<span data-ttu-id="af832-119">설명</span><span class="sxs-lookup"><span data-stu-id="af832-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="af832-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="af832-120">ErrorNumber</span></span>|<span data-ttu-id="af832-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="af832-121">xs:string</span></span>|<span data-ttu-id="af832-122">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="af832-122">The SQL error number.</span></span>|  
|<span data-ttu-id="af832-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="af832-123">AppDomain</span></span>|<span data-ttu-id="af832-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="af832-124">xs:string</span></span>|<span data-ttu-id="af832-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="af832-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
