---
title: 개체 변수 할당(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656060"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="2234e-102">개체 변수 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2234e-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="2234e-103">일반적인 대입문을 사용 하 여 개체 변수에 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="2234e-104">개체 식을 할당할 수 있습니다 또는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="2234e-105">`Nothing` 변수에 할당 된 현재 개체가 없는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="2234e-106">초기화</span><span class="sxs-lookup"><span data-stu-id="2234e-106">Initialization</span></span>  
 <span data-ttu-id="2234e-107">코드를 실행 하 고 변수가 초기화 됩니다 개체를 시작할 때 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="2234e-108">해당 선언 초기화를 포함 하는 것 다시 선언 문이 실행 될 때 지정 된 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="2234e-109">사용 하 여 선언에서 초기화를 포함할 수는 [새로](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="2234e-110">개체 변수를 선언 하는 다음 선언문 `testUri` 및 `ver` 하 고 특정 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="2234e-111">각를 사용 하 여 해당 클래스의 오버 로드 된 생성자 중 하나는 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="2234e-112">연결 해제</span><span class="sxs-lookup"><span data-stu-id="2234e-112">Disassociation</span></span>  
 <span data-ttu-id="2234e-113">개체 변수 설정 `Nothing` 특정 개체 변수 연결이 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="2234e-114">이렇게 하면 실수로 개체 변수를 변경 하 여 변경 하는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="2234e-115">또한 개체 변수는 다음 예제와 같이 유효한 개체를 가리키는 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="2234e-116">변수가 가리키는 개체를 다른 응용 프로그램에 있으면,이 테스트는 해당 응용 프로그램 종료 했거나 개체만 개체를 무효화 하는지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="2234e-117">개체 변수 값이 `Nothing` 라고도 *null 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="2234e-118">현재 인스턴스</span><span class="sxs-lookup"><span data-stu-id="2234e-118">Current Instance</span></span>  
 <span data-ttu-id="2234e-119">*현재 인스턴스가* 는 코드가 현재 실행 중인 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="2234e-120">프로시저 내의 모든 코드가 실행 되는 프로시저가 호출 된 현재 인스턴스의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="2234e-121">`Me` 현재 인스턴스를 참조 하는 개체 변수로 키워드를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="2234e-122">프로시저 없으면 [공유](../../../../visual-basic/language-reference/modifiers/shared.md), 사용할 수 있습니다는 `Me` 키워드 현재 인스턴스에 대 한 포인터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="2234e-123">공유 프로시저 클래스의 특정 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="2234e-124">사용 하 여 `Me` 프로시저 다른 모듈에서 현재 인스턴스를 전달 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="2234e-125">예를 들어 XML 문서 수가 및 일부 표준 텍스트를 모두 추가.</span><span class="sxs-lookup"><span data-stu-id="2234e-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="2234e-126">다음 예제에서는이 작업을 수행 하는 절차를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="2234e-127">그런 다음 모든 XML 문서 개체 프로시저를 호출 하 고 현재 인스턴스를 인수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="2234e-128">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2234e-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2234e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2234e-129">See Also</span></span>  
 [<span data-ttu-id="2234e-130">개체 변수</span><span class="sxs-lookup"><span data-stu-id="2234e-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="2234e-131">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="2234e-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="2234e-132">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="2234e-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="2234e-133">방법: Visual Basic의 개체를 할당 하 고 개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="2234e-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="2234e-134">방법: 개체 변수가 인스턴스를 참조하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2234e-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="2234e-135">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="2234e-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
