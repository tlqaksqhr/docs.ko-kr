---
title: "람다 식(C# 프로그래밍 가이드)"
ms.date: 2017-03-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
caps.latest.revision: 64
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c952c72d9108775fbd0f824f82cacdab5ba91d09
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="b819d-102">람다 식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b819d-102">Lambda Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="b819d-103">람다 식은 [대리자](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) 또는 [식 트리](../../../csharp/programming-guide/delegates/using-delegates.md) 형식을 만드는 데 사용할 수 있는 [익명 함수](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) 입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-103">A lambda expression is an [anonymous function](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) that you can use to create [delegates](../../../csharp/programming-guide/delegates/using-delegates.md) or [expression tree](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) types.</span></span> <span data-ttu-id="b819d-104">람다 식을 사용하여 인수로 전달되거나 함수 호출 값으로 반환되는 로컬 함수를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="b819d-105">람다 식은 LINQ 쿼리 식을 작성하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>  
  
 <span data-ttu-id="b819d-106">람다 식을 만들려면 람다 연산자 [=>](../../../csharp/language-reference/operators/lambda-operator.md)왼쪽에 입력 매개 변수를 지정하고(있는 경우) 다른 쪽에 식이나 문 블록을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="b819d-107">예를 들어 람다 식 `x => x * x` 는 이름이 `x` 인 매개 변수를 지정하고 `x` 제곱 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="b819d-108">다음 예제와 같이 대리자 형식에 이 식을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="b819d-109">식 트리 형식을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b819d-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b819d-110">`=>` 연산자는 대입(`=`)과 우선 순위가 같고 [오른쪽 결합형](../../../csharp/programming-guide/statements-expressions-operators/operators.md)입니다(연산자 문서의 "결합성" 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="b819d-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="b819d-111">람다 식은 메서드 기반 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서 <xref:System.Linq.Enumerable.Where%2A> 같은 표준 쿼리 연산자 메서드의 인수로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="b819d-112"><xref:System.Linq.Enumerable.Where%2A> to Objects 및 <xref:System.Linq.Enumerable> 에서처럼 메서드 기반의 구문을 사용하여 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 클래스에서 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]메서드를 호출하는 경우 매개 변수는 <xref:System.Func%602?displayProperty=fullName>대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=fullName>.</span></span> <span data-ttu-id="b819d-113">람다 식은 이러한 대리자를 만드는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="b819d-114">예를 들어 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서처럼 이 메서드를 <xref:System.Linq.Queryable?displayProperty=fullName> 클래스에서 호출하는 경우 매개 변수 형식은 <xref:System.Linq.Expressions.Expression?displayProperty=fullName><Func\>이고, 여기서 Func는 입력 매개 변수를 16개까지 가질 수 있는 임의의 Func 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=fullName> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=fullName><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="b819d-115">이 경우에도 람다 식을 사용하면 식 트리를 간단하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="b819d-116">람다 식은 `Where` 호출과 비슷하게 보일 수 있지만 실제로 람다 식을 통해 생성되는 개체 형식은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="b819d-117">위의 예제에서 대리자 시그니처는 형식이 암시적으로 지정된 `int`형식의 입력 매개 변수 하나를 포함하고 `int`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="b819d-118">람다 식에도 입력 매개 변수 하나(`x`)와 컴파일러에서 `int` 형식으로 암시적으로 변환할 수 있는 반환 값이 있기 때문에 람다 식을 이 형식의 대리자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="b819d-119">형식 유추는 다음 단원에서 자세하게 설명합니다. 입력 매개 변수를 5로 사용하여 대리자를 호출하면 25라는 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="b819d-120">[is](../../../csharp/language-reference/keywords/is.md) 또는 [as](../../../csharp/language-reference/keywords/as.md) 연산자의 왼쪽에는 람다 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="b819d-121">무명 메서드에 적용되는 모든 제한은 람다 식에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="b819d-122">자세한 내용은 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b819d-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="b819d-123">식 람다</span><span class="sxs-lookup"><span data-stu-id="b819d-123">Expression Lambdas</span></span>  
 <span data-ttu-id="b819d-124">=> 연산자의 오른쪽에 식이 있는 람다 식을 *식 람다*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="b819d-125">식 람다는 [식 트리](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)를 만드는 데 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-125">Expression lambdas are used extensively in the construction of [Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span></span> <span data-ttu-id="b819d-126">식 람다는 식의 결과를 반환하며 기본 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>  
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="b819d-127">괄호는 람다 식에 입력 매개 변수가 하나뿐인 경우에만 생략할 수 있고 그렇지 않으면 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="b819d-128">둘 이상의 입력 매개 변수는 다음과 같이 괄호로 묶고 쉼표로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="b819d-129">컴파일러에서 입력 형식을 유추할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="b819d-130">이와 같은 경우에는 다음 예제와 같이 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```

 <span data-ttu-id="b819d-131">입력 매개 변수가 0개이면 다음과 같이 빈 괄호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-131">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="b819d-132">위의 예제에서 식 람다의 본문은 메서드 호출로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="b819d-133">하지만 SQL Server와 같은 .NET Framework 외부에서 평가되는 식 트리를 만드는 경우에는 람다 식에 메서드 호출을 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="b819d-134">이러한 메서드는 .NET 공용 언어 런타임의 컨텍스트 안에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-134">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="b819d-135">문 람다</span><span class="sxs-lookup"><span data-stu-id="b819d-135">Statement Lambdas</span></span>  
 <span data-ttu-id="b819d-136">문 람다는 다음과 같이 중괄호 안에 문을 지정한다는 점을 제외하면 식 람다와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="b819d-137">(input-parameters) => { statement; }</span><span class="sxs-lookup"><span data-stu-id="b819d-137">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="b819d-138">문 람다의 본문에 지정할 수 있는 문의 개수에는 제한이 없지만 일반적으로 2-3개 정도만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
<span data-ttu-id="b819d-139">[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="b819d-139">[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]</span></span>

<span data-ttu-id="b819d-140">[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="b819d-140">[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]</span></span>

 <span data-ttu-id="b819d-141">무명 메서드와 마찬가지로 문 람다는 식 트리를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-141">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="b819d-142">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="b819d-142">Async Lambdas</span></span>  
 <span data-ttu-id="b819d-143">[async](../../../csharp/language-reference/keywords/async.md) 및 [await](../../../csharp/language-reference/keywords/await.md) 키워드를 사용하여 비동기 처리를 통합하는 람다 식과 문을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-143">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="b819d-144">예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-144">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="b819d-145">비동기 람다를 사용하여 동일한 이벤트 처리기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-145">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="b819d-146">이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `async` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-146">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="b819d-147">비동기 메서드를 만들고 사용하는 방법에 대한 자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b819d-147">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="b819d-148">표준 쿼리 연산자와 람다 식</span><span class="sxs-lookup"><span data-stu-id="b819d-148">Lambdas with the Standard Query Operators</span></span>  
 <span data-ttu-id="b819d-149">대부분의 표준 쿼리 연산자에는 형식이 제네릭 대리자의 <xref:System.Func%602> 패밀리 중 하나인 입력 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-149">Many Standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="b819d-150">이러한 대리자는 형식 매개 변수를 사용하여 입력 매개 변수의 수와 형식 및 대리자의 반환 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-150">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="b819d-151">`Func` 대리자는 소스 데이터 집합에 있는 각 요소에 적용할 사용자 정의 식을 캡슐화하는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-151">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="b819d-152">다음 대리자 형식을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-152">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="b819d-153">이 경우 대리자를 `Func<int,bool> myFunc` 로 인스턴스화할 수 있습니다. 여기서 `int` 는 입력 매개 변수이고, `bool` 은 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-153">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="b819d-154">반환 값은 항상 마지막 형식 매개 변수에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-154">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="b819d-155">`Func<int, string, bool>` 은 두 입력 매개 변수 `int` 및 `string`과 반환 형식 `bool`을 사용하여 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-155">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="b819d-156">다음 `Func` 대리자를 호출하면 입력 매개 변수가 5인지 여부를 나타내는 true 또는 false가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-156">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="b819d-157">System.Linq.Queryable에 정의되어 있는 표준 쿼리 연산자의 경우와 같이 인수 형식이 `Expression<Func>`인 경우에도 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-157">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="b819d-158">`Expression<Func>` 인수를 지정하면 식 트리에 람다 식이 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-158">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="b819d-159">다음 코드에서는 표준 쿼리 연산자인 <xref:System.Linq.Enumerable.Count%2A> 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-159">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="b819d-160">컴파일러에서 입력 매개 변수의 형식을 유추하거나 사용자가 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-160">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="b819d-161">이 람다 식은 2로 나누었을 때 나머지가 1인 정수(`n`)의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-161">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="b819d-162">다음 코드 줄은 숫자 시퀀스에서 조건을 만족하지 않는 첫 번째 숫자가 "9"이기 때문에 `numbers` 배열에서 "9" 왼쪽에 있는 모든 요소가 포함된 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-162">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="b819d-163">이 예제에서는 괄호로 묶어 입력 매개 변수를 여러 개 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-163">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="b819d-164">이 메서드는 값이 해당 위치보다 작은 숫자를 발견할 때까지 숫자 배열의 모든 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-164">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="b819d-165">여기서 람다 연산자(`=>`)를 크거나 같음 연산자(`>=`)와 혼동하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-165">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="b819d-166">람다 식에서의 형식 유추</span><span class="sxs-lookup"><span data-stu-id="b819d-166">Type Inference in Lambdas</span></span>  
 <span data-ttu-id="b819d-167">컴파일러에서는 람다 식 본문, 매개 변수의 대리자 형식 및 C# 언어 사양에 설명되어 있는 기타 요소를 기준으로 형식을 유추할 수 있기 때문에 대부분의 경우에는 람다 식을 작성할 때 입력 매개 변수의 형식을 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-167">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="b819d-168">대부분의 표준 쿼리 연산자에서 첫 번째 입력 형식은 소스 시퀀스 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-168">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="b819d-169">따라서 `IEnumerable<Customer>`를 쿼리할 경우 입력 변수가 `Customer` 개체로 유추됩니다. 이는 이 개체의 메서드와 속성에 액세스할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-169">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="b819d-170">람다 식에는 다음과 같은 일반적인 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-170">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="b819d-171">람다 식과 대리자 형식에 포함된 매개 변수 수가 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-171">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="b819d-172">람다 식의 각 입력 매개 변수는 해당되는 대리자 매개 변수로 암시적으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-172">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="b819d-173">람다 식의 반환 값(있는 경우)은 대리자의 반환 형식으로 암시적으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-173">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="b819d-174">공용 형식 시스템에는 "람다 식"이라는 개념이 기본적으로 포함되어 있지 않기 때문에 람다 식 자체에는 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-174">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="b819d-175">그러나 람다 식의 "형식"을 비공식적으로 언급해야 할 경우도 있는데</span><span class="sxs-lookup"><span data-stu-id="b819d-175">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="b819d-176">이 경우 형식은 대리자 형식 또는 람다 식이 변환되는 <xref:System.Linq.Expressions.Expression> 형식을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-176">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="b819d-177">람다 식의 변수 범위</span><span class="sxs-lookup"><span data-stu-id="b819d-177">Variable Scope in Lambda Expressions</span></span>  
 <span data-ttu-id="b819d-178">람다 식은 람다 함수를 정의하는 메서드 범위 내에 있거나 람다 식을 포함하는 형식 범위 내에 있는 *외부 변수*([무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) 참조)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-178">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="b819d-179">이러한 방식으로 캡처되는 변수는 변수가 범위를 벗어나 가비지 수집되는 경우에도 람다 식에 사용할 수 있도록 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-179">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="b819d-180">외부 변수는 명확하게 할당해야만 람다 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-180">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="b819d-181">다음 예제에서는 이러한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-181">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="b819d-182">람다 식의 변수 범위에는 다음과 같은 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-182">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="b819d-183">캡처된 변수는 해당 변수를 참조하는 대리자가 가비지 수집 대상이 될 때까지 가비지 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-183">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="b819d-184">람다 식에 사용된 변수는 외부 메서드에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-184">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="b819d-185">람다 식은 바깥쪽 메서드에서 `ref` 또는 `out` 매개 변수를 직접 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-185">A lambda expression cannot directly capture a `ref` or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="b819d-186">람다 식의 return 문에 의해서는 바깥쪽 메서드가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-186">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="b819d-187">점프문의 대상이 블록 외부에 있는 경우 람다 식에 람다 함수 내에 있는 `goto` 문, `break` 문 또는 `continue` 문을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-187">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="b819d-188">대상이 블록 내에 있는 경우 람다 함수 블록 외부에 점프문을 사용해도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b819d-188">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b819d-189">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b819d-189">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="b819d-190">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="b819d-190">Featured Book Chapter</span></span>  
 <span data-ttu-id="b819d-191">[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195395) 의 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="b819d-191">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b819d-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b819d-192">See Also</span></span>  
 <span data-ttu-id="b819d-193">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b819d-193">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b819d-194">[LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="b819d-194">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="b819d-195">[무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="b819d-195">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="b819d-196">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="b819d-196">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="b819d-197">[Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) </span><span class="sxs-lookup"><span data-stu-id="b819d-197">[Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) </span></span>  
 <span data-ttu-id="b819d-198">[Visual Studio 2008 C# 샘플(LINQ 샘플 쿼리 파일 및 XQuery 프로그램 참조)](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba) </span><span class="sxs-lookup"><span data-stu-id="b819d-198">[Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba) </span></span>  
 [<span data-ttu-id="b819d-199">재귀 람다 식</span><span class="sxs-lookup"><span data-stu-id="b819d-199">Recursive lambda expressions</span></span>](http://go.microsoft.com/fwlink/?LinkId=112395)

