---
title: REM 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604278"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="a7e9f-102">REM 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7e9f-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="a7e9f-103">프로그램의 소스 코드에 설명 주석을 포함 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7e9f-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="a7e9f-105">요소</span><span class="sxs-lookup"><span data-stu-id="a7e9f-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="a7e9f-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-106">Optional.</span></span> <span data-ttu-id="a7e9f-107">포함할 주석의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-107">The text of any comment you want to include.</span></span> <span data-ttu-id="a7e9f-108">사이 공백을 않습니다는 `REM` 키워드 및 `comment`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7e9f-109">설명</span><span class="sxs-lookup"><span data-stu-id="a7e9f-109">Remarks</span></span>  
 <span data-ttu-id="a7e9f-110">넣을 수는 `REM` 문만 각 줄에 다른 문 다음에 줄에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="a7e9f-111">`REM` 문은 줄에서 마지막 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="a7e9f-112">다른 문의 오는 경우는 `REM` 공백으로 해당 문에서 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="a7e9f-113">작은따옴표를 사용할 수 있습니다 (`'`) 대신 `REM`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="a7e9f-114">의견 다른 문이 같은 줄에 오거나 단독 줄에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7e9f-115">계속할 수 없습니다는 `REM` 줄 연속 시퀀스를 사용 하 여 문 (`_`).</span><span class="sxs-lookup"><span data-stu-id="a7e9f-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="a7e9f-116">주석 시작 되 면 컴파일러는 특별 한 의미에 대 한 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="a7e9f-117">주석이 여러 행에 대 한 다른 사용 `REM` 문이나 주석 기호 (`'`) 각 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7e9f-118">예제</span><span class="sxs-lookup"><span data-stu-id="a7e9f-118">Example</span></span>  
 <span data-ttu-id="a7e9f-119">다음 예제는 `REM` 문이 프로그램에 설명 주석을 포함 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="a7e9f-120">또한 단일 따옴표 문자를 사용 하는 방법도 보여 줍니다 (`'`) 대신 `REM`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e9f-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7e9f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7e9f-121">See Also</span></span>  
 [<span data-ttu-id="a7e9f-122">코드 주석</span><span class="sxs-lookup"><span data-stu-id="a7e9f-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="a7e9f-123">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="a7e9f-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
