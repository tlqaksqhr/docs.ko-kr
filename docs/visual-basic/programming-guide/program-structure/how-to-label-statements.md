---
title: "방법: Label 문(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="d1704-102">방법: Label 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1704-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="d1704-103">문 블록은 콜론으로 구분 된 코드 줄 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="d1704-104">확인 문자열 또는 정수 뒤에 오는 코드의 줄에 있다고 *레이블이*합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="d1704-105">문 레이블은 사용 하기 위해 문 같은 식별 하는 코드 줄을 표시 하는 데 사용 됩니다 `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="d1704-106">레이블은 유효한 Visual Basic 식별자 중 하나가 될 수 있습니다-프로그래밍 요소를 식별 하는 것과 같은-또는 정수 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="d1704-107">소스 코드 줄의 시작 부분에 표시 되어야 합니다 레이블과 같은 줄에서 문에 의해 뒤 여부에 관계 없이 콜론을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="d1704-108">컴파일러는 줄의 시작 모든 미리 정의 된 식별자와 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="d1704-109">그렇지 않은 경우 컴파일러는 레이블을 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="d1704-110">레이블 자신의 선언 공간 있고 다른 식별자를 방해 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="d1704-111">레이블의 범위는 메서드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="d1704-112">레이블 선언 모호한 상황에서는 우선 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1704-113">레이블을은 실행문 메서드 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="d1704-114">에는 코드 줄 레이블을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d1704-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="d1704-115">식별자 뒤에 콜론 소스 코드 줄의 시작 부분에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1704-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="d1704-116">로 다음 코드 줄을 표시 하는 예를 들어 `Jump` 및 `120`각각:</span><span class="sxs-lookup"><span data-stu-id="d1704-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d1704-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1704-117">See Also</span></span>  
 [<span data-ttu-id="d1704-118">문</span><span class="sxs-lookup"><span data-stu-id="d1704-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="d1704-119">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="d1704-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="d1704-120">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="d1704-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
