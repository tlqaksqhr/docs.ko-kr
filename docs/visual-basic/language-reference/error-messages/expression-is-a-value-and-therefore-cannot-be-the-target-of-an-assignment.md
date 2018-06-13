---
title: 식이 값이므로 할당 대상일 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: dd5618bd0533f885a6aef8229b2d8cb1bc34c237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590240"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="0d0e4-102">식이 값이므로 할당 대상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="0d0e4-103">문에서 식에 값을 할당 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="0d0e4-104">런타임 시 쓰기 가능한 변수, 속성 또는 배열 요소에만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="0d0e4-105">다음 예제에서는이 오류가 발생 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="0d0e4-106">유사한 예 속성 및 배열 요소에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="0d0e4-107">**간접 액세스 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d0e4-107">**Indirect Access.**</span></span> <span data-ttu-id="0d0e4-108">값 형식을 통해 간접적으로 액세스도이 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="0d0e4-109">다음 코드 예제 값을 설정 하려고 시도 하는 것이 좋습니다 <xref:System.Drawing.Point> 통해 간접적으로 액세스 하 여 <xref:System.Windows.Forms.Control.Location%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="0d0e4-110">위 예의 마지막 문이 실패에 대 한 임시 할당만을 만들기 때문에 <xref:System.Drawing.Point> 에서 반환 된 구조는 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="0d0e4-111">구조체는 값 형식 및 문이 실행 된 후에 임시 구조 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="0d0e4-112">선언에 대 한 변수를 사용 하 여 문제가 해결 될 <xref:System.Windows.Forms.Control.Location%2A>에 대 한 더 영구적인 할당 만듦는 <xref:System.Drawing.Point> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="0d0e4-113">다음 예제에서는 앞의 예제의 마지막 문으로 대체할 수 있는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="0d0e4-114">**오류 ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="0d0e4-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0d0e4-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0d0e4-115">To correct this error</span></span>  
  
-   <span data-ttu-id="0d0e4-116">문이 값 식에 할당 하는 경우 단일 쓰기 가능한 변수, 속성 또는 배열 요소와 식을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="0d0e4-117">문을 통해 값 형식 (일반적으로 구조)를 통해 간접적으로 액세스를 경우 값 형식을 보유할 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="0d0e4-118">적절 한 구조 (또는 다른 값 형식)를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="0d0e4-119">변수를 사용 하 여 값을 할당 하는 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0e4-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0e4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d0e4-120">See Also</span></span>  
 [<span data-ttu-id="0d0e4-121">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="0d0e4-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="0d0e4-122">문</span><span class="sxs-lookup"><span data-stu-id="0d0e4-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="0d0e4-123">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0d0e4-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
