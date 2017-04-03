---
title: "지연된 실행 예제(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 652ea21bab0bf32e71e270c75d50d53a3a2bbac7
ms.lasthandoff: 03/13/2017


---
# <a name="deferred-execution-example-c"></a>지연된 실행 예제(C#)
이 항목에서는 지연된 실행과 지연 계산이 LINQ to XML 쿼리의 실행에 미치는 영향을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 지연된 실행을 사용하는 확장 메서드를 사용하는 경우의 실행 순서를 보여 줍니다. 이 예제에서는 세 문자열의 배열을 선언한 다음 `ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복합니다.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 `ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복할 때 각 항목이 소스 문자열 배열에서 검색되어 대문자로 변환된 후 다음 항목이 소스 문자열 배열에서 검색됩니다.  
  
 반환된 컬렉션의 각 항목이 `foreach`의 `Main` 루프에서 처리되기 전에는 문자열의 전체 배열이 대문자로 변환되지 않는 것을 확인할 수 있습니다.  
  
 이 자습서의 다음 항목에서는 쿼리를 연결하는 방법을 보여 줍니다.  
  
-   [연결 쿼리 예제(C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서: 여러 쿼리 연결(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
