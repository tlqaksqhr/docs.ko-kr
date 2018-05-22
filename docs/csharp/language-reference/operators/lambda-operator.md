---
title: =&gt; 연산자(C# 참조)
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: d1565e262fbd3ebcee2d1576a2a0c8ed3ba8ce38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="gt-operator-c-reference"></a>=&gt; 연산자(C# 참조)

`=>` 연산자는 C#에서 두 가지 방법으로 사용할 수 있습니다.

- [람다 식](../../lambda-expressions.md)에서 [람다 연산자](#lamba-operator)로, 람다 본문에서 입력 변수를 구분합니다.
 
- [식 본문 정의](#expression-body-definition)에서는 멤버 구현에서 멤버 이름을 구분합니다. 

## <a name="lambda-operator"></a>람다 연산자

`=>` 토큰을 람다 연산자라고 합니다. 이 연산자는 *람다 식*에서 왼쪽의 입력 변수를 오른쪽의 람다 본문과 구분하는 데 사용됩니다. 람다 식은 무명 메서드와 유사한 인라인 식이지만 보다 유연하며, 메서드 구문으로 표현되는 LINQ 쿼리에서 광범위하게 사용됩니다. 자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.  
  
 다음 예제에서는 문자열 배열에서 가장 짧은 문자열 길이를 찾아 표시하는 두 가지 방법을 보여 줍니다. 예제의 첫 번째 부분에서는 람다 식(`w => w.Length`)을 `words` 배열의 각 요소에 적용한 다음 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 가장 짧은 길이를 찾습니다. 비교를 위해 예제의 두 번째 부분에서는 쿼리 구문을 사용하여 동일한 작업을 수행하는 더 긴 솔루션을 보여 줍니다.  
  
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
  
### <a name="remarks"></a>설명  
 `=>` 연산자는 할당 연산자(`=`)와 우선 순위가 같으며 오른쪽 결합성이 있습니다.  
  
 입력 변수의 형식을 명시적으로 지정하거나 컴파일러에서 유추하도록 할 수 있습니다. 두 경우 모두 변수는 컴파일 시간에 강력한 형식이어야 합니다. 다음 예제와 같이 형식을 지정할 때 형식 이름과 변수 이름을 괄호로 묶어야 합니다.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>예  
 다음 예제에서는 두 개의 인수를 사용하는 표준 쿼리 연산자 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>의 오버로드에 대한 람다 식을 작성하는 방법을 보여 줍니다. 람다 식에는 둘 이상의 매개 변수가 사용되므로 매개 변수를 괄호로 묶어야 합니다. 두 번째 매개 변수 `index`는 컬렉션에서 현재 요소의 인덱스를 나타냅니다. `Where` 식은 길이가 배열의 해당 인덱스 위치보다 작은 모든 문자열을 반환합니다.  
  
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
## <a name="expression-body-definition"></a>식 본문 정의

식 본문 정의는 간결하고 읽을 수 있는 형식으로 멤버 구현을 제공합니다. 다음과 같은 일반적인 구문을 포함합니다.

```csharp
member => expression;
```
여기서 *expression*은 유효한 식입니다. *식*은 멤버의 반환 형식이 `void`이거나 멤버가 생성자 또는 종료자인 경우에만 *statement 식*일 수 있습니다.

메서드 및 속성 가져오기 문에 대한 식 본문 정의는 C# 6부터 지원됩니다. 생성자, 종료자, 속성 설정 문 및 인덱서에 대한 식 본문 정의는 C# 7부터 지원됩니다.

`Person.ToString` 메서드에 대한 식 본문 정의는 다음과 같습니다.

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

다음과 같은 메서드 정의의 약식 버전입니다.

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
식 본문 정의에 대한 자세한 내용은 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 참조하세요.

## <a name="see-also"></a>참고 항목  
[C# 참조](../../../csharp/language-reference/index.md)   
[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
[람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)