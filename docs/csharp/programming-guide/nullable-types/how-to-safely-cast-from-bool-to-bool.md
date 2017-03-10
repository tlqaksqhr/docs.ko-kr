---
title: "방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "캐스팅[C#], nullable 형식"
  - "nullable 형식[C#], bool?을 bool로 캐스팅"
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# 방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드)
`bool?` nullable 형식에는 `true`, `false` 및 `null`의 세 가지 값이 포함될 수 있습니다.  따라서 `bool?` 형식은 `if`, `for` 또는 `while` 등이 있는 조건문에서 사용할 수 없습니다.  예를 들어, 다음 코드는 컴파일러 오류를 발생시킵니다.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 이 코드는 `null`이 조건문의 컨텍스트에서 무엇을 의미하는지 명확하지 않기 때문에 컴파일되지 않습니다.  조건문에서 `bool?`를 사용하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 검사하여 값이 `null`이 아닌지 확인한 다음 값을 `bool`로 캐스팅합니다.  자세한 내용은 [bool](../../../csharp/language-reference/keywords/bool.md)을 참조하십시오.  `null` 값을 사용하여 `bool?`에 대한 캐스팅을 수행하면 조건 테스트에서 <xref:System.InvalidOperationException>이 throw됩니다.  다음 예제에서는 `bool?`에서 `bool`로 안전하게 캐스팅할 수 있는 한 가지 방법을 보여 줍니다.  
  
## 예제  
  
```c#  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [리터럴 키워드](../../../csharp/language-reference/keywords/literal-keywords.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [?? 연산자](../../../csharp/language-reference/operators/null-conditional-operator.md)