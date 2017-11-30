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
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="09a38-102">액세스 가능한 &#39; Main &#39; 에 있는 적절 한 시그니처가 메서드가 &#39; &lt;이름&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="09a38-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="09a38-103">명령줄 응용 프로그램에 있어야는 `Sub Main` 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a38-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="09a38-104">`Main`으로 선언 해야 `Public Shared` 또는 클래스에 정의 되어 있는 경우 `Public` 모듈에서 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="09a38-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="09a38-105">대 한 자세한 내용은 `Main`, 참조 [NIB: Visual Basic 버전의 Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)합니다.</span><span class="sxs-lookup"><span data-stu-id="09a38-105">For more information on `Main`, see [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).</span></span>  
  
 <span data-ttu-id="09a38-106">**오류 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="09a38-106">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="09a38-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="09a38-107">To correct this error</span></span>  
  
-   <span data-ttu-id="09a38-108">정의 `Public Sub Main` 프로젝트에 대 한 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="09a38-108">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="09a38-109">로 선언 `Shared` 클래스 내에서 정의 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="09a38-109">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a38-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09a38-110">See Also</span></span>  
 [<span data-ttu-id="09a38-111">NIB: Visual Basic 버전의 Hello, World</span><span class="sxs-lookup"><span data-stu-id="09a38-111">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="09a38-112">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="09a38-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="09a38-113">절차</span><span class="sxs-lookup"><span data-stu-id="09a38-113">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
