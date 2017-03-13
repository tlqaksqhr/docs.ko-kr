---
title: "값 형식 매개 변수 전달(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "메서드 매개 변수[C#], 값 형식"
  - "매개 변수[C#], value"
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 값 형식 매개 변수 전달(C# 프로그래밍 가이드)
[값 형식](../../../csharp/language-reference/keywords/value-types.md) 변수는 데이터에 대한 참조를 포함하는 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md) 변수와는 반대로 데이터를 직접 포함합니다.  메서드에 값\-형식 변수를 값으로 전달 변수의 복사본을 전달 하는 것을 의미 합니다.  메서드에서 변수 변경 매개 변수 없는 인수 변수에 저장할 원본 데이터에 영향을 주지.  호출된 된 메서드의 매개 변수 값을 변경 하려면 참조로 전달 해야 합니다 사용 하는  [ref](../../../csharp/language-reference/keywords/ref.md) 또는  [out](../../../csharp/language-reference/keywords/out.md) 키워드.  편의상 다음 예제에서는 `ref`를 사용합니다.  
  
## 값으로 값 형식 전달  
 다음 예제에서는 값으로 값\-형식 매개 변수를 전달하는 것에 대해 설명합니다.  변수 `n`는 값으로 메서드 `SquareIt`에 전달됩니다.  메서드 안에서의 변경 사항은 변수의 원래 값에 영향을 주지 않습니다.  
  
 [!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 변수 `n` 는 값 형식입니다.  값 데이터를 포함 `5`.  `SquareIt`를 호출하면 `n`의 내용은 매개 변수 `x`에 복사되어 메서드에서 제곱됩니다.  그러나 `Main`, 값을 `n` 호출한 후 하는 것은 `SquareIt` 메서드 되었습니다 하기 전에.  메서드 내에 발생 하는 변경 지역 변수에 영향을 미칩니다 `x`.  
  
## 참조로 참조 형식 전달  
 으로 인수가 전달 된다는 것을 제외 하 고 다음 예제는 이전 예제와 동일한 것은 `ref` 매개 변수.  기본 인수 값 `n`, 시기 변경 됩니다 `x` 메서드에서 변경 됩니다.  
  
 [!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 이 예제에서 전달되는 것은 `n`의 값이 아니라 `n`에 대한 참조입니다.  매개 변수 `x`는 [int](../../../csharp/language-reference/keywords/int.md)가 아니라 `int`에 대한 참조\(이 경우에는 `n`에 대한 참조\)입니다.  따라서, `x` 제곱 메서드 내에서 실제로 제곱 되 란 `x` 참조 `n`.  
  
## 값 형식 맞바꾸기  
 인수 값을 변경 하는 일반적인 예는 두 변수를 메서드에 전달 하 고 메서드 내용을 맞바꿉니다 swap 메서드를입니다.  Swap 메서드를 인수를 참조로 전달 해야 합니다.  그렇지 않으면 메서드 안에서 매개 변수의 로컬 복사본을 바꿉니다 및 호출 하는 메서드를 변경 되지 발생 합니다.  다음 예제에서는 정수 값을 바꿉니다.  
  
 [!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 호출 하면 해당 `SwapByRef` 메서드를 사용은 `ref` 키워드 다음에 호출을 다음 예제와 같이.  
  
 [!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [참조 형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)