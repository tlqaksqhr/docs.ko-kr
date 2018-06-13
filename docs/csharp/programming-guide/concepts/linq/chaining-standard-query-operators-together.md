---
title: 여러 표준 쿼리 연산자 연결(C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 9e59c12873b8e8afeaad43b8ffbe400b43b55747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326152"
---
# <a name="chaining-standard-query-operators-together-c"></a>여러 표준 쿼리 연산자 연결(C#)
이 항목은 [자습서: 쿼리 연결(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) 자습서의 마지막 항목입니다.  
  
 표준 쿼리 연산자도 연결할 수 있습니다. 예를 들어, <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 연산자를 삽입할 수 있으며 이 연산자는 지연 방식으로 작동합니다. 이 연산자는 중간 결과를 유형화하지 않습니다.  
  
## <a name="example"></a>예  
 이 예제에서 <xref:System.Linq.Enumerable.Where%2A> 메서드는 `ConvertCollectionToUpperCase`를 호출하기 전에 호출됩니다. <xref:System.Linq.Enumerable.Where%2A> 메서드는 이 자습서의 이전 예제에서 사용되는 지연 메서드인 `ConvertCollectionToUpperCase` 및 `AppendString`과 거의 똑같은 방식으로 작동합니다.  
  
 한 가지 차이점은 이 경우에 <xref:System.Linq.Enumerable.Where%2A> 메서드는 소스 컬렉션을 반복하고 첫 번째 항목이 조건자를 통과하지 않는 것을 확인한 다음 조건자를 통과하는 다음 항목을 가져옵니다. 그런 다음 두 번째 항목을 반환합니다.  
  
 그러나 기본 개념은 동일합니다. 중간 컬렉션이 유형화될 필요가 없으면 유형화되지 않습니다.  
  
 쿼리 식이 사용되는 경우 쿼리 식은 표준 쿼리 연산자에 대한 호출로 변환되고 동일한 원칙이 적용됩니다.  
  
 Office Open XML 문서를 쿼리하는 이 단원의 모든 예제에서는 동일한 원칙을 사용합니다. 지연된 실행과 지연 계산은 LINQ와 LINQ to XML을 효과적으로 사용하기 위해 이해해야 하는 기본 개념입니다.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            where s.CompareTo("D") >= 0  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a>참고 항목  
 [자습서: 여러 쿼리 연결(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
