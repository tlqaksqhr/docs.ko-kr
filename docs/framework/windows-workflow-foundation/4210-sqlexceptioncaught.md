---
title: 4210 - SqlExceptionCaught
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a3fb3c780b80172db8770e717f517b97608fcb7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="f5347-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="f5347-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="f5347-103">속성</span><span class="sxs-lookup"><span data-stu-id="f5347-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5347-104">ID</span><span class="sxs-lookup"><span data-stu-id="f5347-104">ID</span></span>|<span data-ttu-id="f5347-105">4210</span><span class="sxs-lookup"><span data-stu-id="f5347-105">4210</span></span>|  
|<span data-ttu-id="f5347-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f5347-106">Keywords</span></span>|<span data-ttu-id="f5347-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f5347-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f5347-108">수준</span><span class="sxs-lookup"><span data-stu-id="f5347-108">Level</span></span>|<span data-ttu-id="f5347-109">경고</span><span class="sxs-lookup"><span data-stu-id="f5347-109">Warning</span></span>|  
|<span data-ttu-id="f5347-110">채널</span><span class="sxs-lookup"><span data-stu-id="f5347-110">Channel</span></span>|<span data-ttu-id="f5347-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f5347-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5347-112">설명</span><span class="sxs-lookup"><span data-stu-id="f5347-112">Description</span></span>  
 <span data-ttu-id="f5347-113">SQL 예외가 catch되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5347-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5347-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f5347-114">Message</span></span>  
 <span data-ttu-id="f5347-115">SQL 예외 %1번 메시지 %2을(를) catch했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5347-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5347-116">설명</span><span class="sxs-lookup"><span data-stu-id="f5347-116">Details</span></span>  
  
|<span data-ttu-id="f5347-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f5347-117">Data Item Name</span></span>|<span data-ttu-id="f5347-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f5347-118">Data Item Type</span></span>|<span data-ttu-id="f5347-119">설명</span><span class="sxs-lookup"><span data-stu-id="f5347-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5347-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="f5347-120">ErrorNumber</span></span>|<span data-ttu-id="f5347-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5347-121">xs:string</span></span>|<span data-ttu-id="f5347-122">SQL 오류 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f5347-122">The SQL error number.</span></span>|  
|<span data-ttu-id="f5347-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="f5347-123">ExceptionMessage</span></span>|<span data-ttu-id="f5347-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5347-124">xs:string</span></span>|<span data-ttu-id="f5347-125">SQL 예외로부터의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f5347-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="f5347-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5347-126">AppDomain</span></span>|<span data-ttu-id="f5347-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5347-127">xs:string</span></span>|<span data-ttu-id="f5347-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5347-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
