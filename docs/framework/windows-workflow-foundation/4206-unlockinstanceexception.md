---
title: 4206 - UnlockInstanceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 385dd784d5b52de42202e9f9d47f16650873a71d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="a57a3-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="a57a3-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="a57a3-103">속성</span><span class="sxs-lookup"><span data-stu-id="a57a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a57a3-104">ID</span><span class="sxs-lookup"><span data-stu-id="a57a3-104">ID</span></span>|<span data-ttu-id="a57a3-105">4206</span><span class="sxs-lookup"><span data-stu-id="a57a3-105">4206</span></span>|  
|<span data-ttu-id="a57a3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a57a3-106">Keywords</span></span>|<span data-ttu-id="a57a3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="a57a3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="a57a3-108">수준</span><span class="sxs-lookup"><span data-stu-id="a57a3-108">Level</span></span>|<span data-ttu-id="a57a3-109">오류</span><span class="sxs-lookup"><span data-stu-id="a57a3-109">Error</span></span>|  
|<span data-ttu-id="a57a3-110">채널</span><span class="sxs-lookup"><span data-stu-id="a57a3-110">Channel</span></span>|<span data-ttu-id="a57a3-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="a57a3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a57a3-112">설명</span><span class="sxs-lookup"><span data-stu-id="a57a3-112">Description</span></span>  
 <span data-ttu-id="a57a3-113">인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a57a3-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a57a3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="a57a3-114">Message</span></span>  
 <span data-ttu-id="a57a3-115">인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="a57a3-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a57a3-116">설명</span><span class="sxs-lookup"><span data-stu-id="a57a3-116">Details</span></span>  
  
|<span data-ttu-id="a57a3-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a57a3-117">Data Item Name</span></span>|<span data-ttu-id="a57a3-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a57a3-118">Data Item Type</span></span>|<span data-ttu-id="a57a3-119">설명</span><span class="sxs-lookup"><span data-stu-id="a57a3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a57a3-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="a57a3-120">ExceptionMessage</span></span>|<span data-ttu-id="a57a3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a57a3-121">xs:string</span></span>|<span data-ttu-id="a57a3-122">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="a57a3-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="a57a3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a57a3-123">AppDomain</span></span>|<span data-ttu-id="a57a3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a57a3-124">xs:string</span></span>|<span data-ttu-id="a57a3-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a57a3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
