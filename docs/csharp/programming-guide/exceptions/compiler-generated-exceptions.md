---
title: "컴파일러 생성 예외(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외[C#], 컴파일러 생성"
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 컴파일러 생성 예외(C# 프로그래밍 가이드)
기본 작업이 실패하면 몇 가지 예외가 .NET Framework의 CLR\(공용 언어 런타임\)에서 자동으로 throw됩니다.  다음 표에서는 이러한 예외와 오류 조건을 보여 줍니다.  
  
|Exception|설명|  
|---------------|--------|  
|<xref:System.ArithmeticException>|<xref:System.DivideByZeroException> 및 <xref:System.OverflowException> 등의 산술 연산 과정에서 발생하는 예외에 대한 기본 클래스|  
|<xref:System.ArrayTypeMismatchException>|저장된 요소의 실제 형식이 배열의 실제 형식과 호환되지 않기 때문에 배열에서 해당 요소를 저장하지 못하는 경우|  
|<xref:System.DivideByZeroException>|정수 계열 값을 0으로 나누려고 한 경우|  
|<xref:System.IndexOutOfRangeException>|배열을 인덱싱하려 할 때 인덱스가 0보다 작거나 배열 경계를 벗어난 경우|  
|<xref:System.InvalidCastException>|런타임에 기본 형식에서 인터페이스나 파생 형식으로의 명시적 변환이 실패한 경우|  
|<xref:System.NullReferenceException>|값이 [null](../../../csharp/language-reference/keywords/null.md)인 개체를 참조할 경우|  
|<xref:System.OutOfMemoryException>|[new](../../../csharp/language-reference/keywords/new-operator.md) 연산자를 사용하여 메모리를 할당하는 데 실패한 경우.  이는 공용 언어 런타임에 사용할 수 있는 메모리가 부족하다는 것을 의미합니다.|  
|<xref:System.OverflowException>|`checked` 컨텍스트에서 산술 연산이 오버플로된 경우|  
|<xref:System.StackOverflowException>|보류된 메서드 호출이 너무 많아서 실행 스택이 부족한 경우. 일반적으로 너무 깊은 재귀 호출이나 무한 재귀 호출을 나타냅니다.|  
|<xref:System.TypeInitializationException>|정적 생성자가 예외를 throw했지만 이를 catch할 `catch` 절이 없는 경우|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)