---
title: "변환 연산자 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "변환 연산자[C#]"
  - "변환[C#], 연산자"
  - "명시적 변환 연산자[C#]"
  - "암시적 변환 연산자[C#]"
  - "연산자[C#], 변환"
  - "사용자 정의 변환[C#]"
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 변환 연산자 사용(C# 프로그래밍 가이드)
쉽게 사용할 수 있는 `implicit` 변환 연산자나 또는 변환한 타입의 코드를 읽는 사람에게 명확하게 나타나는 `explicit` 변환 연산자를 사용할 수 있습니다.  여기서 변환 연산자의 형식을 모두 보여줍니다.  
  
> [!NOTE]
>  단순 형식 변환기에 대한 정보를 보실려면, [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), 혹은 <xref:System.Convert> 를 참조하세요.  
  
## 예제  
 다음 코드는 명시적 변환 연산자의 예입니다.  이 연산자는 <xref:System.Byte> 형식을 `Digit`라는 값 형식으로 변환합니다.  모든 바이트를 숫자로 변환할 수 있는 것은 아니므로 이 변환은 명시적입니다. 즉, `Main` 메서드에서와 같이 캐스트를 사용해야 합니다.  
  
 [!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## 예제  
 이 예제에서는 암시적 변환 연산자를 보여 줍니다. 이를 위해 이전 예제에서 수행한 작업을 실행 취소하는 변환 연산자를 정의합니다. 이 예제에서는 `Digit`이라는 값 클래스를 정수 계열 <xref:System.Byte> 형식으로 변환합니다.  모든 숫자를 <xref:System.Byte>로 변환할 수 있으므로 사용자에게 변환 사실을 명시적으로 알릴 필요가 없습니다.  
  
 [!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [is](../../../csharp/language-reference/keywords/is.md)