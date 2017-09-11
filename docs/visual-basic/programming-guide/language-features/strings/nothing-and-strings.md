---
title: "Visual Basic의 nothing 및 문자열 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2d7685c688e96b506cfc2ddddc44ce534625e3b7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="eca48-102">Visual Basic의 Nothing 및 문자열</span><span class="sxs-lookup"><span data-stu-id="eca48-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="eca48-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 런타임 및 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 평가 `Nothing` 다르게 때는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eca48-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="eca48-104">Visual Basic 런타임 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="eca48-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="eca48-105">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca48-105">Consider the following example:</span></span>  
  
 <span data-ttu-id="eca48-106">[!code-vb[VbVbalrStrings #&47;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eca48-106">[!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]</span></span>  
  
 <span data-ttu-id="eca48-107">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 공용 언어 런타임은 일반적으로 평가 `Nothing` 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="eca48-107">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="eca48-108">그러나 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 존재 하지 않는 한 문자열 작업을 수행 하려고 시도 될 때마다 예외를 throw `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="eca48-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca48-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eca48-109">See Also</span></span>  
 [<span data-ttu-id="eca48-110">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="eca48-110">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
