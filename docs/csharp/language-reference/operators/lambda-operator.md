---
title: "=&gt; 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
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
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="e6aa6-102">=&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e6aa6-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="e6aa6-103">`=>` 토큰을 람다 연산자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="e6aa6-104">이 연산자는 *람다 식*에서 왼쪽의 입력 변수를 오른쪽의 람다 본문과 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="e6aa6-105">람다 식은 무명 메서드와 유사한 인라인 식이지만 보다 유연하며, 메서드 구문으로 표현되는 LINQ 쿼리에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="e6aa6-106">자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="e6aa6-107">다음 예제에서는 문자열 배열에서 가장 짧은 문자열 길이를 찾아 표시하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="e6aa6-108">예제의 첫 번째 부분에서는 람다 식(`w => w.Length`)을 `words` 배열의 각 요소에 적용한 다음 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 가장 짧은 길이를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="e6aa6-109">비교를 위해 예제의 두 번째 부분에서는 쿼리 구문을 사용하여 동일한 작업을 수행하는 더 긴 솔루션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="e6aa6-110">설명</span><span class="sxs-lookup"><span data-stu-id="e6aa6-110">Remarks</span></span>  
 <span data-ttu-id="e6aa6-111">`=>` 연산자는 할당 연산자(`=`)와 우선 순위가 같으며 오른쪽 결합성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="e6aa6-112">입력 변수의 형식을 명시적으로 지정하거나 컴파일러에서 유추하도록 할 수 있습니다. 두 경우 모두 변수는 컴파일 시간에 강력한 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="e6aa6-113">다음 예제와 같이 형식을 지정할 때 형식 이름과 변수 이름을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="e6aa6-114">예제</span><span class="sxs-lookup"><span data-stu-id="e6aa6-114">Example</span></span>  
 <span data-ttu-id="e6aa6-115">다음 예제에서는 두 개의 인수를 사용하는 표준 쿼리 연산자 <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>의 오버로드에 대한 람다 식을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="e6aa6-116">람다 식에는 둘 이상의 매개 변수가 사용되므로 매개 변수를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="e6aa6-117">두 번째 매개 변수 `index`는 컬렉션에서 현재 요소의 인덱스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="e6aa6-118">`Where` 식은 길이가 배열의 해당 인덱스 위치보다 작은 모든 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6aa6-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6aa6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6aa6-119">See Also</span></span>  
 <span data-ttu-id="e6aa6-120">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6aa6-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6aa6-121">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6aa6-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e6aa6-122">람다 식</span><span class="sxs-lookup"><span data-stu-id="e6aa6-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

