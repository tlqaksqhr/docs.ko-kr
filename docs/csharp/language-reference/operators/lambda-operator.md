---
title: "=&gt; 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "=>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "람다 연산자[C#]"
  - "=> 연산자[C#]"
  - "람다 식[C#], => 연산자"
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# =&gt; 연산자(C# 참조)
`=>` 토큰을 람다 연산자라고 합니다.  이 연산자를 *람다 식*에 사용하여 오른쪽의 람다 본문과 왼쪽의 입력 변수를 구분합니다.  람다 식은 익명 메서드와 비슷한 인라인 식이지만 보다 유연하며 메서드 구문으로 표현되는 LINQ 쿼리에서 광범위하게 사용됩니다.  자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하십시오.  
  
 찾기 및 문자열의 배열에서 가장 짧은 문자열의 길이 표시 하는 두 가지 예제를 보여 줍니다.  예제의 첫 번째 부분은 람다 식을 적용 \(`w => w.Length`\)의 각 요소는 `words` 배열 및 사용 하는 <xref:System.Linq.Enumerable.Min%2A> 메서드는 최소 길이를.  비교에 대 한 쿼리 구문을 사용 하 여 동일한 작업을 수행 하는 긴 솔루션 예제의 두 번째 부분을 보여 줍니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## 설명  
 `=>` 연산자는 할당 연산자\(`=`\)와 우선 순위가 같으며 오른쪽 결합성이 있습니다.  
  
 입력 변수의 형식을 명시적으로 지정 하거나 컴파일러에서 유추할 수 있습니다. 어느 경우 든 변수는 컴파일 타임에 강력한.  형식을 지정할 때 형식 이름과 변수 이름을 괄호로 다음 예제와 같이 묶어야 합니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## 예제  
 다음 예제에서는 표준 쿼리 연산자의 오버 로드에 대 한 람다 식을 작성 하는 방법을 보여 줍니다. <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> 는 두 개의 인수를 사용 합니다.  람다 식 매개 변수가 두 개 이상 있기 때문에 매개 변수를 괄호로 묶어야 합니다.  두 번째 매개 변수를 `index`를 현재 컬렉션에 있는 요소의 인덱스를 나타냅니다.  `Where` 식은 길이가 배열의 해당 인덱스 위치 보다 작은 모든 문자열을 반환 합니다.  
  
```c#  
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
  
    // Compare the following code, which arrives at the same list of short  
    // digits but takes more work to get there.  
    Console.WriteLine("\nExample that uses a for loop:");  
    List<string> shortDigits2 = new List<string>();  
    for (var i = 0; i < digits.Length; i++)  
    {  
        if (digits[i].Length < i)  
            shortDigits2.Add(digits[i]);  
    }  
  
    foreach (var d in shortDigits2)  
    {  
        Console.WriteLine(d);  
    }  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
  
    // Example that uses a for loop:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)