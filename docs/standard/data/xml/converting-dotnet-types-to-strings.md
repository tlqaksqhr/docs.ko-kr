---
title: ".NET Framework 형식을 문자열로 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3abe140e62f112a15a1ad1b1b2a79c14364b26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="44883-102">.NET Framework 형식을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="44883-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="44883-103">.NET Framework 형식을 문자열로 변환 하려면 사용 된 **ToString** 메서드.</span><span class="sxs-lookup"><span data-stu-id="44883-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="44883-104">**ToString** 메서드에 전달 된 형식이의 문자열 표현을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44883-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="44883-105">다음 표에서는 XSD(XML 스키마) 사양에 대응하는 형식으로 문자열을 반환하는 .NET Framework 형식의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44883-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="44883-106">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="44883-106">.NET Framework type</span></span>|<span data-ttu-id="44883-107">반환된 문자열 형식</span><span class="sxs-lookup"><span data-stu-id="44883-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="44883-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="44883-108">Boolean</span></span>|<span data-ttu-id="44883-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="44883-109">"true", "false"</span></span>|  
|<span data-ttu-id="44883-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="44883-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="44883-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="44883-111">"INF"</span></span>|  
|<span data-ttu-id="44883-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="44883-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="44883-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="44883-113">"-INF"</span></span>|  
|<span data-ttu-id="44883-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="44883-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="44883-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="44883-115">"INF"</span></span>|  
|<span data-ttu-id="44883-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="44883-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="44883-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="44883-117">"-INF"</span></span>|  
|<span data-ttu-id="44883-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="44883-118">DateTime</span></span>|<span data-ttu-id="44883-119">형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="44883-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="44883-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="44883-120">Timespan</span></span>|<span data-ttu-id="44883-121">형식은 PnYnMnTnHnMnS입니다. 예를 들어, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44883-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44883-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44883-122">See Also</span></span>  
 [<span data-ttu-id="44883-123">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="44883-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="44883-124">문자열을.NET Framework 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="44883-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
