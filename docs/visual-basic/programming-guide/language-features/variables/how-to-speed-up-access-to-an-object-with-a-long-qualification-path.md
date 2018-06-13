---
title: '방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650201"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="9f365-102">방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f365-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="9f365-103">여러 메서드 및 속성의 정규화 경로가 필요로 하는 개체를 자주 액세스 하는 경우 있습니다 속도를 높일 수 코드 정규화 된 경로 반복 하지 않음으로써 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="9f365-104">두 가지 방법으로 반복 되는 정규화 된 경로 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="9f365-105">개체를 변수에 할당할 수 있습니다 또는에서 사용할 수는 `With`... `End With` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="9f365-106">속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체를 변수에 할당 하 여</span><span class="sxs-lookup"><span data-stu-id="9f365-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="9f365-107">자주 액세스 하는 개체 유형의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="9f365-108">선언의 초기화 부분에 정규화 된 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="9f365-109">변수를 사용 하 여 개체의 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f365-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="9f365-110">속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체는 With를 사용 하 여... End With 블록</span><span class="sxs-lookup"><span data-stu-id="9f365-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="9f365-111">정규화 된 경로에 배치 된 `With` 문.</span><span class="sxs-lookup"><span data-stu-id="9f365-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="9f365-112">내부 개체의 멤버 액세스는 `With` 차단 하기 전에 `End With` 문.</span><span class="sxs-lookup"><span data-stu-id="9f365-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f365-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f365-113">See Also</span></span>  
 [<span data-ttu-id="9f365-114">개체 변수</span><span class="sxs-lookup"><span data-stu-id="9f365-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="9f365-115">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="9f365-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
