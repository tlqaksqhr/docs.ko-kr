---
title: "방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="4ed43-102">방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ed43-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="4ed43-103">여러 메서드 및 속성의 정규화 경로가 필요로 하는 개체를 자주 액세스 하는 경우 있습니다 속도를 높일 수 코드 정규화 된 경로 반복 하지 않음으로써 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="4ed43-104">두 가지 방법으로 반복 되는 정규화 된 경로 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="4ed43-105">개체를 변수에 할당할 수 있습니다 또는에서 사용할 수는 `With`... `End With` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="4ed43-106">속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체를 변수에 할당 하 여</span><span class="sxs-lookup"><span data-stu-id="4ed43-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="4ed43-107">자주 액세스 하는 개체 유형의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="4ed43-108">선언의 초기화 부분에 정규화 된 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="4ed43-109">변수를 사용 하 여 개체의 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed43-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="4ed43-110">속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체는 With를 사용 하 여... End With 블록</span><span class="sxs-lookup"><span data-stu-id="4ed43-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="4ed43-111">정규화 된 경로에 배치 된 `With` 문.</span><span class="sxs-lookup"><span data-stu-id="4ed43-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="4ed43-112">내부 개체의 멤버 액세스는 `With` 차단 하기 전에 `End With` 문.</span><span class="sxs-lookup"><span data-stu-id="4ed43-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4ed43-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ed43-113">See Also</span></span>  
 [<span data-ttu-id="4ed43-114">개체 변수</span><span class="sxs-lookup"><span data-stu-id="4ed43-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="4ed43-115">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="4ed43-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
