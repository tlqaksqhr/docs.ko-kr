---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f430e7b58d5aba277b0a35a20f1f5fdb707bce9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="96918-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="96918-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="96918-103">속성</span><span class="sxs-lookup"><span data-stu-id="96918-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96918-104">ID</span><span class="sxs-lookup"><span data-stu-id="96918-104">ID</span></span>|<span data-ttu-id="96918-105">1013</span><span class="sxs-lookup"><span data-stu-id="96918-105">1013</span></span>|  
|<span data-ttu-id="96918-106">키워드</span><span class="sxs-lookup"><span data-stu-id="96918-106">Keywords</span></span>|<span data-ttu-id="96918-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="96918-107">WFRuntime</span></span>|  
|<span data-ttu-id="96918-108">수준</span><span class="sxs-lookup"><span data-stu-id="96918-108">Level</span></span>|<span data-ttu-id="96918-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="96918-109">Verbose</span></span>|  
|<span data-ttu-id="96918-110">채널</span><span class="sxs-lookup"><span data-stu-id="96918-110">Channel</span></span>|<span data-ttu-id="96918-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="96918-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96918-112">설명</span><span class="sxs-lookup"><span data-stu-id="96918-112">Description</span></span>  
 <span data-ttu-id="96918-113">ExecuteActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96918-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="96918-114">메시지</span><span class="sxs-lookup"><span data-stu-id="96918-114">Message</span></span>  
 <span data-ttu-id="96918-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96918-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96918-116">설명</span><span class="sxs-lookup"><span data-stu-id="96918-116">Details</span></span>  
  
|<span data-ttu-id="96918-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="96918-117">Data Item Name</span></span>|<span data-ttu-id="96918-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="96918-118">Data Item Type</span></span>|<span data-ttu-id="96918-119">설명</span><span class="sxs-lookup"><span data-stu-id="96918-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96918-120">동작</span><span class="sxs-lookup"><span data-stu-id="96918-120">Activity</span></span>|<span data-ttu-id="96918-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="96918-121">xs:string</span></span>|<span data-ttu-id="96918-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="96918-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="96918-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="96918-123">DisplayName</span></span>|<span data-ttu-id="96918-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="96918-124">xs:string</span></span>|<span data-ttu-id="96918-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="96918-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="96918-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="96918-126">InstanceId</span></span>|<span data-ttu-id="96918-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="96918-127">xs:string</span></span>|<span data-ttu-id="96918-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="96918-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="96918-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96918-129">AppDomain</span></span>|<span data-ttu-id="96918-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="96918-130">xs:string</span></span>|<span data-ttu-id="96918-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="96918-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
