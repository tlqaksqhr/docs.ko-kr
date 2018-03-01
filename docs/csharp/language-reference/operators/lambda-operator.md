---
title: "=&gt; 연산자(C# 참조)"
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="7faf8-102">=&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7faf8-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="7faf8-103">`=>` 연산자는 C#에서 두 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="7faf8-104">로 [람다 연산자](#lamba-operator) 에 [람다 식을](../../lambda-expressions.md), 람다 본문에서 입력된 변수를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="7faf8-105">에 [식 본문 정의](#expression-body-definition), 멤버 이름은 멤버 구현에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="7faf8-106">람다 연산자</span><span class="sxs-lookup"><span data-stu-id="7faf8-106">Lambda operator</span></span>

<span data-ttu-id="7faf8-107">`=>` 토큰을 람다 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="7faf8-108">이 연산자는 *람다 식*에서 왼쪽의 입력 변수를 오른쪽의 람다 본문과 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="7faf8-109">람다 식은 무명 메서드와 유사한 인라인 식이지만 보다 유연하며, 메서드 구문으로 표현되는 LINQ 쿼리에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="7faf8-110">자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7faf8-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="7faf8-111">다음 예제에서는 문자열 배열에서 가장 짧은 문자열 길이를 찾아 표시하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="7faf8-112">예제의 첫 번째 부분에서는 람다 식(`w => w.Length`)을 `words` 배열의 각 요소에 적용한 다음 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 가장 짧은 길이를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="7faf8-113">비교를 위해 예제의 두 번째 부분에서는 쿼리 구문을 사용하여 동일한 작업을 수행하는 더 긴 솔루션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a><span data-ttu-id="7faf8-114">설명</span><span class="sxs-lookup"><span data-stu-id="7faf8-114">Remarks</span></span>  
 <span data-ttu-id="7faf8-115">`=>` 연산자는 할당 연산자(`=`)와 우선 순위가 같으며 오른쪽 결합성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="7faf8-116">입력 변수의 형식을 명시적으로 지정하거나 컴파일러에서 유추하도록 할 수 있습니다. 두 경우 모두 변수는 컴파일 시간에 강력한 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="7faf8-117">다음 예제와 같이 형식을 지정할 때 형식 이름과 변수 이름을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="7faf8-118">예제</span><span class="sxs-lookup"><span data-stu-id="7faf8-118">Example</span></span>  
 <span data-ttu-id="7faf8-119">다음 예제에서는 두 개의 인수를 사용하는 표준 쿼리 연산자 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>의 오버로드에 대한 람다 식을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="7faf8-120">람다 식에는 둘 이상의 매개 변수가 사용되므로 매개 변수를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="7faf8-121">두 번째 매개 변수 `index`는 컬렉션에서 현재 요소의 인덱스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="7faf8-122">`Where` 식은 길이가 배열의 해당 인덱스 위치보다 작은 모든 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
## <a name="expression-body-definition"></a><span data-ttu-id="7faf8-123">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="7faf8-123">Expression body definition</span></span>

<span data-ttu-id="7faf8-124">식 본문 정의 읽을 수 있는 고도로 압축 된 형식 멤버의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="7faf8-125">다음 일반적인 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="7faf8-126">여기서 *expression*은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="7faf8-127">*식* 수는 *statement 식* 멤버의 반환 형식이 전용 `void`, 또는 멤버 생성자 또는 종료 자가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="7faf8-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="7faf8-128">식 본문 정의 메서드 및 속성 get 문을 실행 하는 것에 대 한 C# 6부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="7faf8-129">식 본문 정의 생성자, 종료자에 대 한 set 문, 속성 및 인덱서는 C# 7부터 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="7faf8-130">다음은에 대 한 식 본문 정의 `Person.ToString` 메서드:</span><span class="sxs-lookup"><span data-stu-id="7faf8-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="7faf8-131">다음과 같은 메서드 정의의 약식 버전은</span><span class="sxs-lookup"><span data-stu-id="7faf8-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="7faf8-132">식 본문 정의 대 한 정보를 자세한 참조 [멤버 식 본문이](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7faf8-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7faf8-133">See Also</span></span>  
<span data-ttu-id="7faf8-134">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7faf8-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="7faf8-135">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7faf8-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="7faf8-136">[람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="7faf8-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="7faf8-137">[멤버 식 본문이](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7faf8-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>