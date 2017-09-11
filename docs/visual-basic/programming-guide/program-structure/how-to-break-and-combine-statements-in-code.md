---
title: "방법: (Visual Basic) 코드에서 문 분리 및 결합 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ca281035a0bd81a9b52cdd60f2bc59724852709
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="dddfe-102">방법: 코드에서 문 분리 및 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dddfe-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="dddfe-103">코드를 작성할 때 코드 편집기에서 가로로 스크롤하면 볼 수 있는 긴 문을 시간에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="dddfe-104">방식에 영향을 주지 않지만 코드를 실행, 하기 어렵습니다 사용자나 다른 사람이 모니터에 표시 된 대로 코드를 읽는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="dddfe-105">이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="dddfe-106">단일 문에 여러 줄으로 중단 하려면</span><span class="sxs-lookup"><span data-stu-id="dddfe-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="dddfe-107">밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="dddfe-108">밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dddfe-109">경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="dddfe-110">줄 연속 문자를 생략할 수 있는 구문 요소 목록은 "암시적 줄 연속 문자"의 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="dddfe-111">다음 예제에서는 문이 마지막 줄을 제외한 모든 줄 연속 문자로 네 줄으로 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     <span data-ttu-id="dddfe-112">[!code-vb[VbVbcnConventions #&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dddfe-112">[!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span></span>  
  
     <span data-ttu-id="dddfe-113">이 시퀀스를 사용 하 여 하면 온라인 및 때 인쇄 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-113">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="dddfe-114">줄 연속 문자에는 줄에서 마지막 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-114">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="dddfe-115">같은 줄에 언제나 그렇듯 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-115">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="dddfe-116">줄 연속 문자입니다; 사용할 수 있는 대 한 몇 가지 제한 사항이 예를 들어 중간 인수 이름에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-116">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="dddfe-117">줄 연속 문자를 인수 목록을 분리할 수 있지만 개별 인수 이름에는 그대로 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-117">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="dddfe-118">줄 연속 문자를 사용 하 여 메모를 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-118">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="dddfe-119">컴파일러의 특별 한 의미에 대 한 주석 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-119">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="dddfe-120">주석이 여러 행에 대 한 반복 주석 기호 (`'`) 각 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-120">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="dddfe-121">일반적으로 각 문을 별도 줄에는 권장된 방법 이지만 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 같은 줄에 여러 개의 문을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-121">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="dddfe-122">여러 개의 문을 같은 줄에 배치 하려면</span><span class="sxs-lookup"><span data-stu-id="dddfe-122">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="dddfe-123">각 문을 콜론 (`:`) 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="dddfe-123">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     <span data-ttu-id="dddfe-124">[!code-vb[VbVbcnConventions #&10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dddfe-124">[!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dddfe-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dddfe-125">See Also</span></span>  
 <span data-ttu-id="dddfe-126">[프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="dddfe-126">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="dddfe-127"> [문](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="dddfe-127"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>
