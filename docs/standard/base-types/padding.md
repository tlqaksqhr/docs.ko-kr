---
title: ".NET에서 문자열 채우기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="5eae4-102">.NET에서 문자열 채우기</span><span class="sxs-lookup"><span data-stu-id="5eae4-102">Padding Strings in .NET</span></span>
<span data-ttu-id="5eae4-103">다음 중 하나를 사용 하 여 <xref:System.String> 선행 또는 후행 문자 지정한 길이를 채운 원래 문자열에 구성 된 새 문자열을 만드는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="5eae4-104">채움 문자는 공백이나 지정된 문자를 사용할 수 있고 결과적으로 오른쪽에 맞춤인지 아니면 왼쪽 맞춤인지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="5eae4-105">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="5eae4-105">Method name</span></span>|<span data-ttu-id="5eae4-106">기능</span><span class="sxs-lookup"><span data-stu-id="5eae4-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="5eae4-107">선행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="5eae4-108">후행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="5eae4-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="5eae4-109">PadLeft</span></span>  
 <span data-ttu-id="5eae4-110"><xref:System.String.PadLeft%2A?displayProperty=nameWithType> 메서드를 원래 문자열에 지정 된 전체 길이 맞도록 충분 한 선행 채움 문자를 연결 하 여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="5eae4-111"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> 방법은 채움 문자를 공백을 사용 및 <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 메서드를 사용 하면 사용자 고유의 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="5eae4-112">다음 코드 예제에서는 <xref:System.String.PadLeft%2A> 메서드 20 자는 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="5eae4-113">이 예제에서는 콘솔에 "`--------Hello World!`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="5eae4-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="5eae4-114">PadRight</span></span>  
 <span data-ttu-id="5eae4-115"><xref:System.String.PadRight%2A?displayProperty=nameWithType> 메서드를 원래 문자열에 지정 된 전체 길이 맞도록 필요한 만큼 후행 채움 문자를 연결 하 여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="5eae4-116"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> 방법은 채움 문자를 공백을 사용 및 <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 메서드를 사용 하면 사용자 고유의 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="5eae4-117">다음 코드 예제에서는 <xref:System.String.PadRight%2A> 메서드 20 자는 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="5eae4-118">이 예제에서는 콘솔에 "`Hello World!--------`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5eae4-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5eae4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eae4-119">See Also</span></span>  
 [<span data-ttu-id="5eae4-120">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="5eae4-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
