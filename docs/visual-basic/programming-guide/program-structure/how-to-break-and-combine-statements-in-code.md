---
title: "방법: 코드에서 문 분리 및 결합(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf6b3ce7e5f9549ca04c4980bd3c91513b343ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="caeff-102">방법: 코드에서 문 분리 및 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caeff-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="caeff-103">코드를 작성할 시간에 가로 스크롤 코드 편집기에서 볼 수 있는 긴 문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="caeff-104">방식에 영향을 주지 않지만 코드를 실행, 하기 쉽게 없는 사용자나 다른 사람이 모니터에 표시 된 대로 코드를 읽을 수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="caeff-105">이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="caeff-106">단일 문에 여러 선으로 분할 하려면</span><span class="sxs-lookup"><span data-stu-id="caeff-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="caeff-107">밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 원하는 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="caeff-108">밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="caeff-109">경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="caeff-110">"암시적 줄 연속" 목록이 줄 연속 문자를 생략할 수 있는 구문 요소에 대 한 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="caeff-111">다음 예에서 문의 마지막 줄을 제외한 모든 줄 연속 문자로 네 줄으로 나뉘어집니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     <span data-ttu-id="caeff-112">이 시퀀스를 사용 하면 온라인 및 시기 인쇄 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="caeff-113">줄 연속 문자는 줄에서 마지막 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="caeff-114">같은 줄에 다른 문자로 올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="caeff-115">줄 연속 문자를 사용할 수 있는 대 한 몇 가지 제한 사항이 예를 들어 인수 이름 중에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="caeff-116">인수 목록이 줄 연속 문자를 중단할 수 있지만 개별 인수 이름에는 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="caeff-117">줄 연속 문자를 사용 하 여 메모를 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="caeff-118">컴파일러 특별 한 의미에 대 한 설명의 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="caeff-119">주석이 여러 행에 대 한 반복 주석 기호 (`'`) 각 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="caeff-120">권장 되는 방법에는 일반적으로 별도 줄에 각 문을 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 같은 줄에 여러 개의 문을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-120">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="caeff-121">같은 줄에 여러 개의 문을 배치 하려면</span><span class="sxs-lookup"><span data-stu-id="caeff-121">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="caeff-122">문을 콜론으로 분리 (`:`) 다음 예제와 같이, 합니다.</span><span class="sxs-lookup"><span data-stu-id="caeff-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="caeff-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="caeff-123">See Also</span></span>  
 [<span data-ttu-id="caeff-124">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="caeff-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="caeff-125">문</span><span class="sxs-lookup"><span data-stu-id="caeff-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
