---
title: "방법: 리플렉션을 사용하여 어셈블리의 메타데이터 쿼리(LINQ)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15fbed050c35dbe7c31eaa61accefe96d4b15da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-an-assembly39s-metadata-with-reflection-linq-c"></a>방법: 리플렉션을 사용하여 어셈블리의 메타데이터 쿼리(LINQ)(C#)
다음 예제에서는 리플렉션과 함께 LINQ를 사용하여 지정된 검색 조건과 일치하는 메서드에 대한 특정 메타데이터를 검색하는 방법을 보여 줍니다. 이 경우 쿼리는 배열과 같은 열거 가능한 형식을 반환하는 모든 메서드의 이름을 어셈블리에서 검색합니다.  
  
## <a name="example"></a>예제  
  
```csharp  
using System.Reflection;  
using System.IO;  
namespace LINQReflection  
{  
    class ReflectionHowTO  
    {  
        static void Main(string[] args)  
        {  
            Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
            var pubTypesQuery = from type in assembly.GetTypes()  
                        where type.IsPublic  
                            from method in type.GetMethods()  
                            where method.ReturnType.IsArray == true   
                                || ( method.ReturnType.GetInterface(  
                                    typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                                && method.ReturnType.FullName != "System.String" )  
                            group method.ToString() by type.ToString();  
  
            foreach (var groupOfMethods in pubTypesQuery)  
            {  
                Console.WriteLine("Type: {0}", groupOfMethods.Key);  
                foreach (var method in groupOfMethods)  
                {  
                    Console.WriteLine("  {0}", method);  
                }  
            }  
  
            Console.WriteLine("Press any key to exit");  
            Console.ReadKey();  
        }  
    }    
}  
```  
  
 이 예제에서는 <xref:System.Reflection.Assembly.GetTypes%2A> 메서드를 사용하여 지정된 어셈블리의 형식 배열을 반환합니다. public 형식만 반환되도록 [where](../../../../csharp/language-reference/keywords/where-clause.md) 필터가 적용됩니다. 각 public 형식에 대해 <xref:System.Type.GetMethods%2A> 호출에서 반환된 <xref:System.Reflection.MethodInfo> 배열을 사용하여 하위 쿼리가 생성됩니다. 이러한 결과는 해당 반환 형식이 배열이거나 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 형식인 메서드만 반환하도록 필터링됩니다. 마지막으로, 이러한 결과는 형식 이름을 키로 사용하여 그룹화됩니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
