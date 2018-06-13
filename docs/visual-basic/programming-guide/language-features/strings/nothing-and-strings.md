---
title: Visual Basic의 Nothing 및 문자열
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647193"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="24803-102">Visual Basic의 Nothing 및 문자열</span><span class="sxs-lookup"><span data-stu-id="24803-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="24803-103">Visual Basic 런타임 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 평가 `Nothing` 문자열에 나올 때와 다르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="24803-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="24803-104">Visual Basic 런타임 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="24803-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="24803-105">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24803-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="24803-106">Visual Basic 런타임 일반적으로 평가 `Nothing` 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="24803-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="24803-107">그러나 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 하지 않는 고에 문자열 작업을 수행 하려고 시도 될 때마다 예외를 throw `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="24803-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24803-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24803-108">See Also</span></span>  
 [<span data-ttu-id="24803-109">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="24803-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
