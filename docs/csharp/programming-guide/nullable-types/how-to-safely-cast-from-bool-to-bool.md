---
title: '방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: e04e34abd477730f9dd01486ec6bddcde4943edc
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>방법: bool?에서 bool로 안전하게 캐스팅(C# 프로그래밍 가이드)
`bool?` nullable 형식은 세 가지 값 `true`, `false` 및 `null`을 포함할 수 있습니다. 따라서 `bool?` 형식은 `if`, `for` 또는 `while`과 같은 조건에 사용할 수 없습니다. 예를 들어 다음 코드는 컴파일러 오류를 발생시킵니다.  
  
```csharp  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 조건부의 컨텍스트에서 `null`이 의미하는 내용이 명확하지 않으므로 이는 허용되지 않습니다. 조건문에 `bool?`를 사용하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 점검하여 해당 값이 `null`이 아닌지 확인한 다음, `bool`로 캐스팅합니다. 자세한 내용은 [bool](../../../csharp/language-reference/keywords/bool.md)을 참조하세요. 값이 `null`인 `bool?`에 대해 캐스팅을 수행하면 조건 테스트에서 <xref:System.InvalidOperationException>이 throw됩니다. 다음 예제에서는 `bool?`에서 `bool`로 안전하게 캐스팅하는 한 가지 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
  
```csharp  
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
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [리터럴 키워드](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
 [?? 연산자](../../../csharp/language-reference/operators/null-coalescing-operator.md)
