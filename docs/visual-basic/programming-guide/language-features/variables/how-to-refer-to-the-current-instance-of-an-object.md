---
title: '방법: 개체의 현재 인스턴스 참조(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648361"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="e67eb-102">방법: 개체의 현재 인스턴스 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e67eb-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="e67eb-103">*현재 인스턴스가* 는 코드가 현재 실행 중인 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e67eb-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="e67eb-104">사용 된 `Me` 키워드를 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67eb-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="e67eb-105">현재 인스턴스 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="e67eb-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="e67eb-106">사용 하 여는 `Me` 키워드 일반적으로 사용 되는 개체 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e67eb-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="e67eb-107">하지만 `Me` 개체 처럼 동작 변수를 선언할 수 없거나 값을 할당할 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67eb-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="e67eb-108">`Me` 항상 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67eb-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67eb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e67eb-109">See Also</span></span>  
 [<span data-ttu-id="e67eb-110">개체 변수</span><span class="sxs-lookup"><span data-stu-id="e67eb-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="e67eb-111">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="e67eb-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="e67eb-112">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="e67eb-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
