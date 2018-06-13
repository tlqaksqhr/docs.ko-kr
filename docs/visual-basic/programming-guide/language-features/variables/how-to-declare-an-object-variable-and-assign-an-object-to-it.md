---
title: '방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648878"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="d9de7-102">방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당</span><span class="sxs-lookup"><span data-stu-id="d9de7-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="d9de7-103">형식의 변수를 선언한는 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 지정 하 여 `As Object` 에 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="d9de7-104">등호 뒤에 개체를 배치 하 여 이러한 변수를 개체를 할당 (`=`) 대입문 이나 초기화 절에서.</span><span class="sxs-lookup"><span data-stu-id="d9de7-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9de7-105">예제</span><span class="sxs-lookup"><span data-stu-id="d9de7-105">Example</span></span>  
 <span data-ttu-id="d9de7-106">다음 예제에서는 선언는 `Object` 변수와 현재 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="d9de7-107">선언 및 할당 변수 선언의 일부로 초기화 하 여 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="d9de7-108">다음 예제에서는 앞의 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9de7-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d9de7-109">Compiling the Code</span></span>  
 <span data-ttu-id="d9de7-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-110">This example requires:</span></span>  
  
-   <span data-ttu-id="d9de7-111"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d9de7-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="d9de7-112">클래스, 구조체 또는 모듈을 작성할는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="d9de7-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="d9de7-113">할당 문을 배치 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d9de7-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9de7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9de7-114">See Also</span></span>  
 [<span data-ttu-id="d9de7-115">변수 선언</span><span class="sxs-lookup"><span data-stu-id="d9de7-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="d9de7-116">개체 변수</span><span class="sxs-lookup"><span data-stu-id="d9de7-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="d9de7-117">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="d9de7-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="d9de7-118">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d9de7-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="d9de7-119">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d9de7-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="d9de7-120">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="d9de7-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d9de7-121">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="d9de7-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
