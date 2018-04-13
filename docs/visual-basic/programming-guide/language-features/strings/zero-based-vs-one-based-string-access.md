---
title: Vs 0부터 시작 합니다. Visual Basic에서 하나 기반 문자열 액세스
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="7248d-102">Vs 0부터 시작 합니다. Visual Basic에서 하나 기반 문자열 액세스</span><span class="sxs-lookup"><span data-stu-id="7248d-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="7248d-103">이 항목에서는 비교 방법을 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 문자열의 문자에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-103">This topic compares how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="7248d-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 항상는 문자열의 문자에 대 한 0부터 시작 액세스를 제공 하지만 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 함수에 따라 0부터 시작 하 고 1부터 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="7248d-105">1부터 시작</span><span class="sxs-lookup"><span data-stu-id="7248d-105">One-Based</span></span>  
 <span data-ttu-id="7248d-106">1부터 시작에 대 한 예제 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 함수를 고려해 야는 `Mid` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-106">For an example of a one-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="7248d-107">부분 문자열은 시작할 위치 1부터 시작 문자 위치를 나타내는 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="7248d-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 문자의 인덱스 부분 문자열을 시작 하려면 문자열이 위치 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="7248d-109">따라서 "ABCDE" 문자열이 있는 경우 개별 문자 번호는 함께 사용할 1,2,3,4,5는 `Mid` 함수가 있지만 함께 사용할 0,1,2,3,4는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="7248d-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="7248d-110">0부터 시작</span><span class="sxs-lookup"><span data-stu-id="7248d-110">Zero-Based</span></span>  
 <span data-ttu-id="7248d-111">0부터 시작에 대 한 예제 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 함수를 고려해 야는 `Split` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-111">For an example of a zero-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="7248d-112">문자열을 분할 하 고 부분 문자열이 포함 된 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7248d-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 문자열을 분할 및 부분 문자열이 포함 된 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7248d-114">때문에 `Split` 함수 및 <xref:System.String.Split%2A> 메서드 반환 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 배열은 0부터 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7248d-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7248d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7248d-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="7248d-116">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="7248d-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
