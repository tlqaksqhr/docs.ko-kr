---
title: "Visual Basic의 Nothing 및 문자열"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="7e565-102">Visual Basic의 Nothing 및 문자열</span><span class="sxs-lookup"><span data-stu-id="7e565-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="7e565-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 런타임 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 평가 `Nothing` 문자열에 나올 때와 다르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e565-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="7e565-104">Visual Basic 런타임 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="7e565-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="7e565-105">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e565-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="7e565-106">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 공용 언어 런타임은 일반적으로 평가 `Nothing` 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="7e565-106">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="7e565-107">그러나 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 하지 않는 고에 문자열 작업을 수행 하려고 시도 될 때마다 예외를 throw `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e565-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e565-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e565-108">See Also</span></span>  
 [<span data-ttu-id="7e565-109">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="7e565-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
