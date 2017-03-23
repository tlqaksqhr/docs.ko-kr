---
title: "sizeof(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sizeof_CSharpKeyword"
  - "sizeof"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sizeof 키워드[C#]"
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# sizeof(C# 참조)
관리되지 않는 형식에 대한 바이트 단위의 크기를 가져오는 데 사용됩니다.  관리되지 않는 형식에는 다음 표에 나열된 기본 제공 형식뿐 아니라 다음 형식도 포함됩니다.  
  
-   열거형 형식  
  
-   포인터 형식  
  
-   참조 형식인 필드나 속성을 포함하지 않는 사용자 정의 구조체  
  
 다음 예제에서는 `int`의 크기를 검색하는 방법을 보여 줍니다.  
  
```c#  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## 설명  
 C\# 버전 2.0부터는 기본 제공 형식에 `sizeof`를 적용할 때 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 모드를 사용하지 않아도 됩니다.  
  
 `sizeof` 연산자는 오버로드되지 않습니다.  `sizeof` 연산자가 반환하는 값은 `int` 형식입니다.  다음 표에서는 특정 기본 제공 형식을 피연산자로 사용하는 `sizeof` 식 대신 사용되는 상수 값을 보여 줍니다.  
  
|식|상수 값|  
|-------|----------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2\(유니코드\)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 구조체를 포함한 다른 모든 형식의 경우에는 안전하지 않은 코드 블록에서만 `sizeof` 연산자를 사용할 수 있습니다.  <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> 메서드를 사용할 수 있지만 이 메서드가 반환하는 값이 `sizeof`가 반환하는 값과 항상 같지는 않습니다.  <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>는 형식이 마샬링된 후의 크기를 반환하지만, `sizeof`는 패딩을 포함하여 공용 언어 런타임에서 할당된 크기를 반환합니다.  
  
## 예제  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)