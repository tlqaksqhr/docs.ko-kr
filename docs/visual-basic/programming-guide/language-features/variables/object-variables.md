---
title: Visual Basic의 개체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649115"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="4c6b2-102">Visual Basic의 개체 변수</span><span class="sxs-lookup"><span data-stu-id="4c6b2-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="4c6b2-103">값을 직접 저장 하는 것 외에도 변수 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="4c6b2-104">변수에 값을 할당할 같은 이유로 변수에 개체 할당:</span><span class="sxs-lookup"><span data-stu-id="4c6b2-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="4c6b2-105">변수 이름은 메서드 및 개체 자체에 액세스 하는 데 필요한 속성의 전체 경로 보다 기억 하기 쉽고 자주입니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="4c6b2-106">개체를 참조 하는 변수를 사용 하 여 반복 해 서 필요한 메서드 또는 속성을 통해 개체 자체를 액세스할 때 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="4c6b2-107">코드를 실행 하는 동안 다른 개체를 참조 하는 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="4c6b2-108">코드 길이 줄이기</span><span class="sxs-lookup"><span data-stu-id="4c6b2-108">Making Code Shorter</span></span>  
 <span data-ttu-id="4c6b2-109">개체 변수를 입력 해야 하는 코드를 단축할 수 있습니다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="4c6b2-110">다음 예제에서는 메서드 및 속성의 전체 경로 사용 하 여 액세스 하는 <xref:System.Windows.Forms.Control> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="4c6b2-111">이 코드를 줄이고 실행 속도를 높일, 컨트롤에 대 한 개체 변수를 사용 하는 경우 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="4c6b2-112">여기에 할당 하려는 특정 클래스와 개체 변수를 선언 해야 합니다 (`Control` 이 경우).</span><span class="sxs-lookup"><span data-stu-id="4c6b2-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="4c6b2-113">개체를 변수에 할당 하면으로 처리할 수 있습니다 완전히 동일 참조 하는 개체를 다룰 때와 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="4c6b2-114">설정 또는 개체의 속성을 검색 하거나 해당 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="4c6b2-115">다음 예제에서는 앞의 예제에서 코드를 단순화 하는 개체 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c6b2-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c6b2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c6b2-116">See Also</span></span>  
 [<span data-ttu-id="4c6b2-117">변수 선언</span><span class="sxs-lookup"><span data-stu-id="4c6b2-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="4c6b2-118">방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선</span><span class="sxs-lookup"><span data-stu-id="4c6b2-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="4c6b2-119">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="4c6b2-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="4c6b2-120">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="4c6b2-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="4c6b2-121">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="4c6b2-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
