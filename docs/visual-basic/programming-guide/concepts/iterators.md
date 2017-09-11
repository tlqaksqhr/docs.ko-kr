---
title: "반복기 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c38609878c10ff3234b5a33ec44d678d24c11d7f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="iterators-visual-basic"></a><span data-ttu-id="69556-102">반복기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69556-102">Iterators (Visual Basic)</span></span>
<span data-ttu-id="69556-103">*반복기* 컬렉션을 나열 하 고 배열 같은 단계별로 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="69556-104">반복기 메서드 또는 `get` 접근자 컬렉션 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="69556-105">반복기 메서드에서 사용 하 여는 [생성](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 각 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="69556-106">경우는 `Yield` 문에 도달 하면, 코드에서 현재 위치 기억 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69556-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="69556-107">실행이 다시 시작 해당 위치에서 다음에 반복기 함수가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69556-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="69556-108">클라이언트 코드에서 반복기를 사용 하 여 소비는 [각각에 대해... 다음](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문 또는 LINQ 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="69556-109">다음 예제에서는의 첫 번째 반복에에서는 `For Each` 루프 하면 실행이 계속는 `SomeNumbers` 첫 번째 때까지 반복기 메서드 `Yield` 문이 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="69556-110">이 반복 3의 값을 반환 하 고 반복기 메서드의 현재 위치는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69556-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="69556-111">어디에서 계속 반복기 메서드의 실행 하는 루프의 다음 반복에서 중단, 다시에 도달할 때 실행을 중지 한 `Yield` 문.</span><span class="sxs-lookup"><span data-stu-id="69556-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="69556-112">이 반복 값 5 반환 하 고 반복기 메서드 내의 현재 위치는 다시 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="69556-113">루프는 반복기 메서드의 끝에 도달 하면 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69556-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 <span data-ttu-id="69556-114">반복기 메서드의 반환 형식 또는 `get` 접근자 수 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="69556-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="69556-115">사용할 수는 `Exit Function` 또는 `Return` 문을 반복을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="69556-116">Visual Basic 반복기 함수 또는 `get` 접근자 선언에 포함 되어 있는 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
 <span data-ttu-id="69556-117">반복기는 Visual Studio 2012의 Visual Basic에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="69556-118">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="69556-118">**In this topic**</span></span>  
  
-   [<span data-ttu-id="69556-119">단순 반복기</span><span class="sxs-lookup"><span data-stu-id="69556-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="69556-120">컬렉션 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="69556-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="69556-121">Try 블록</span><span class="sxs-lookup"><span data-stu-id="69556-121">Try Blocks</span></span>](#BKMK_TryBlocks)  
  
-   [<span data-ttu-id="69556-122">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="69556-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)  
  
-   [<span data-ttu-id="69556-123">제네릭 목록과 함께 반복기 사용</span><span class="sxs-lookup"><span data-stu-id="69556-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="69556-124">구문 정보</span><span class="sxs-lookup"><span data-stu-id="69556-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="69556-125">기술 구현</span><span class="sxs-lookup"><span data-stu-id="69556-125">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="69556-126">반복기 사용</span><span class="sxs-lookup"><span data-stu-id="69556-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="69556-127">단순 반복기 예제를 제외 하 고 항목의 모든 예제에 대 한 포함 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 에 대 한 문을 `System.Collections` 및 `System.Collections.Generic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="69556-128"><a name="BKMK_SimpleIterator"></a>단순 반복기</span><span class="sxs-lookup"><span data-stu-id="69556-128"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="69556-129">다음 예제에는 단일 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="69556-130">`Main`의 각 반복에서 `For Each` 문 본문에서 다음 단계로 진행 하는 반복기 함수에 대 한 호출을 만듭니다 `Yield` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
##  <span data-ttu-id="69556-131"><a name="BKMK_CollectionClass"></a>컬렉션 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="69556-131"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="69556-132">다음 예제에서는 `DaysOfTheWeek` 클래스가 구현 하는 <xref:System.Collections.IEnumerable>인터페이스를 필요로 하는 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="69556-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="69556-133">컴파일러는 암시적으로 호출 된 `GetEnumerator` <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator> 를 반환 하는 메서드</span><span class="sxs-lookup"><span data-stu-id="69556-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="69556-134">`GetEnumerator` 메서드를 사용 하 여 한 번에 하나의 각 문자열을 반환는 `Yield` 문 및 `Iterator` 한정자는 함수 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 <span data-ttu-id="69556-135">다음 예제에서는 한 `Zoo` 동물의 컬렉션을 포함 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="69556-136">`For Each` 클래스 인스턴스를 참조 하는 문 (`theZoo`) 암시적으로 호출 된 `GetEnumerator` 메서드.</span><span class="sxs-lookup"><span data-stu-id="69556-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="69556-137">`For Each` 를 참조 하는 문에 `Birds` 및 `Mammals` 속성 사용은 `AnimalsForType` 반복기 메서드 라는 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
##  <span data-ttu-id="69556-138"><a name="BKMK_TryBlocks"></a>Try 블록</span><span class="sxs-lookup"><span data-stu-id="69556-138"><a name="BKMK_TryBlocks"></a> Try Blocks</span></span>  
 <span data-ttu-id="69556-139">Visual Basic에서는 `Yield` 문에서 `Try` 블록는 [시도 중... Catch... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="69556-140">A `Try` 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="69556-141">다음 예제에서는 포함 `Try`, `Catch`, 및 `Finally` 반복기 함수를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="69556-142">`Finally` 반복기 함수에는 블록이 실행 하기 전에 `For Each` 반복 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 <span data-ttu-id="69556-143">A `Yield` 문 내 야는 `Catch` 블록 또는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="69556-144">하는 경우는 `For Each` 본문 (반복기 메서드) 하는 대신 예외를 throw 한 `Catch` 블록 반복기 함수에이 실행 되지 않으면 하지만 `Finally` 반복기 함수 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69556-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="69556-145">A `Catch` 반복기 함수 내의 블록 반복기 함수 내 발생 하는 예외에만 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
##  <span data-ttu-id="69556-146"><a name="BKMK_AnonymousMethods"></a>무명 메서드</span><span class="sxs-lookup"><span data-stu-id="69556-146"><a name="BKMK_AnonymousMethods"></a> Anonymous Methods</span></span>  
 <span data-ttu-id="69556-147">Visual basic에서는 익명 함수는 반복기 함수를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="69556-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-148">The following example illustrates this.</span></span>  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 <span data-ttu-id="69556-149">다음 예제에는 인수의 유효성을 검사 하는 반복기가 아닌 메서드.</span><span class="sxs-lookup"><span data-stu-id="69556-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="69556-150">메서드는 컬렉션 요소에 설명 하는 익명 반복기의 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 <span data-ttu-id="69556-151">첫 번째 반복이 시작 될 때까지 유효성 검사를 수행할 수 없습니다 이면 유효성 검사 대신 반복기 함수 내에서 `For Each` 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>  
  
##  <span data-ttu-id="69556-152"><a name="BKMK_GenericList"></a>제네릭 목록과 함께 반복기 사용</span><span class="sxs-lookup"><span data-stu-id="69556-152"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="69556-153">다음 예제에서는 `Stack(Of T)` 제네릭 클래스가 구현 하는 <xref:System.Collections.Generic.IEnumerable%601>제네릭 인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="69556-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="69556-154">`Push` 형식의 배열에 값을 할당 하는 메서드 `T`합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="69556-155"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>메서드를 사용 하 여 배열 값을 반환 된 `Yield` 문.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="69556-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>  
  
 <span data-ttu-id="69556-156">제네릭 외에도 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>메서드, 제네릭이 아닌 <xref:System.Collections.IEnumerable.GetEnumerator%2A>도 구현 해야 합니다.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="69556-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="69556-157">즉, <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> 에서 상속</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="69556-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="69556-158">제네릭이 아닌 구현 제네릭 구현의 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69556-158">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="69556-159">예제에서는 데이터의 동일한 컬렉션을 반복 하는 다양 한 방법을 지원 하기 위해 명명 된 반복기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="69556-160">이러한 반복기 명명 되는 `TopToBottom` 및 `BottomToTop` 속성 및 `TopN` 메서드.</span><span class="sxs-lookup"><span data-stu-id="69556-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="69556-161">`BottomToTop` 속성 선언에서 `Iterator` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
  
```  
  
##  <span data-ttu-id="69556-162"><a name="BKMK_SyntaxInformation"></a>구문 정보</span><span class="sxs-lookup"><span data-stu-id="69556-162"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="69556-163">반복기는 방법으로 발생할 수 또는 `get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="69556-164">반복기는 이벤트, 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="69556-165">식 형식에서 암시적 변환이 있어야 합니다.는 `Yield` 문을 반복기의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="69556-166">Visual Basic의 반복기 메서드를 사용할 수 없습니다 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="69556-167">Visual Basic에서 "생성" 예약어 아니며에 사용 될 때만 특별 한 의미가 있는 `Iterator` 메서드 또는 `get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>  
  
##  <span data-ttu-id="69556-168"><a name="BKMK_Technical"></a>기술 구현</span><span class="sxs-lookup"><span data-stu-id="69556-168"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="69556-169">반복기를 메서드로 작성 해도 컴파일러도 변환 중첩된 클래스 즉, 실제로 상태 시스템.</span><span class="sxs-lookup"><span data-stu-id="69556-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="69556-170">이 클래스는 동안 반복기의 위치는 추적 `For Each...Next` 클라이언트 코드에서 루프를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="69556-171">컴파일러의 용도 확인 하려면 반복기 메서드에 대해 생성 되는 Microsoft 중간 언어 코드를 보려면 Ildasm.exe 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="69556-172">에 대 한 반복기를 만들 때 한 [클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md), 전체를 구현할 필요가 없습니다 <xref:System.Collections.IEnumerator>인터페이스.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="69556-172">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="69556-173">컴파일러에서 반복기를 발견 하면 자동으로 생성 된 `Current`, `MoveNext`, 및 `Dispose` 의 메서드는 <xref:System.Collections.IEnumerator>또는 <xref:System.Collections.Generic.IEnumerator%601>인터페이스.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="69556-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="69556-174">각 연속 반복에는 `For Each…Next` 루프 (또는 직접 호출이 `IEnumerator.MoveNext`), 이전 후 다음 반복기 코드 본문을 다시 시작 `Yield` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="69556-175">다음 다음 계속 `Yield` 반복기 본문의 끝에 도달할 때까지 문을 때까지 또는 `Exit Function` 또는 `Return` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>  
  
 <span data-ttu-id="69556-176">반복기를 지원 하지 않는 <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>메서드.</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="69556-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="69556-177">처음부터 다시 반복, 새 반복기를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-177">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="69556-178">자세한 내용은 참조는 [Visual Basic 언어 사양](../../../visual-basic/reference/language-specification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
##  <span data-ttu-id="69556-179"><a name="BKMK_UseOfIterators"></a>반복기 사용</span><span class="sxs-lookup"><span data-stu-id="69556-179"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="69556-180">반복기를 사용 하면의 단순성을 유지 관리할 수는 `For Each` 복잡 한 코드는 목록 순서를 채우는 데 사용 해야 하는 경우 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="69556-181">다음을 수행 하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-181">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="69556-182">목록 순서는 첫 번째 이후 수정 `For Each` 루프 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>  
  
-   <span data-ttu-id="69556-183">첫 번째 반복 하기 전에 큰 목록 완전히 로드 되지 않도록는 `For Each` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="69556-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="69556-184">예로 페이징된 fetch 테이블 행 일괄 처리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69556-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="69556-185">또 다른 예로 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>메서드는.NET Framework 내에서 반복기를 구현 하는.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A></span><span class="sxs-lookup"><span data-stu-id="69556-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="69556-186">반복기에서 목록 작성을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="69556-187">반복기 메서드의 목록을 빌드하고 루프에서 각 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="69556-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69556-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69556-188">See Also</span></span>  
 <span data-ttu-id="69556-189"><xref:System.Collections.Generic></xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="69556-189"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="69556-190"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="69556-190"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="69556-191"> [각각에 대해... Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="69556-191"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="69556-192"> [Yield 문](../../../visual-basic/language-reference/statements/yield-statement.md) </span><span class="sxs-lookup"><span data-stu-id="69556-192"> [Yield Statement](../../../visual-basic/language-reference/statements/yield-statement.md) </span></span>  
<span data-ttu-id="69556-193"> [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)</span><span class="sxs-lookup"><span data-stu-id="69556-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span></span>
