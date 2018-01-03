---
title: "액세스 가능한 &#39; Main &#39; 에 있는 적절 한 시그니처가 메서드가 &#39; &lt;이름&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6a2d66c860b72bd3ef59c02f548ac563fab6b8c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="88f65-102">액세스 가능한 &#39; Main &#39; 에 있는 적절 한 시그니처가 메서드가 &#39; &lt;이름&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="88f65-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="88f65-103">명령줄 응용 프로그램에 있어야는 `Sub Main` 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f65-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="88f65-104">`Main`으로 선언 해야 `Public Shared` 또는 클래스에 정의 되어 있는 경우 `Public` 모듈에서 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="88f65-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="88f65-105">**오류 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="88f65-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88f65-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="88f65-106">To correct this error</span></span>  
  
-   <span data-ttu-id="88f65-107">정의 `Public Sub Main` 프로젝트에 대 한 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="88f65-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="88f65-108">로 선언 `Shared` 클래스 내에서 정의 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f65-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f65-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88f65-109">See Also</span></span>  
 [<span data-ttu-id="88f65-110">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="88f65-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="88f65-111">절차</span><span class="sxs-lookup"><span data-stu-id="88f65-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
