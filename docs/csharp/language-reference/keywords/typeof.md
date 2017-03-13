---
title: "typeof(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof 키워드[C#]"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# typeof(C# 참조)
형식에 대한 `System.Type` 개체를 얻는 데 사용됩니다.  `typeof` 식의 형식은 다음과 같습니다.  
  
```  
System.Type type = typeof(int);  
```  
  
## 설명  
 식의 런타임 형식을 얻으려면 다음 예제와 같이 .NET Framework 메서드 <xref:System.Object.GetType%2A>을 사용합니다.  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 `typeof` 연산자는 오버로드되지 않습니다.  
  
 `typeof` 연산자는 열린 제네릭 형식에도 사용할 수 있습니다.  형식 매개 변수가 둘 이상인 형식을 지정할 때는 적절한 수의 쉼표를 사용해야 합니다.  다음 예제에서는 메서드의 반환 형식이 제네릭 <xref:System.Collections.Generic.IEnumerable%601>인지 여부를 확인하는 방법을 보여 줍니다.  메서드는 MethodInfo 형식의 인스턴스라고 가정합니다.  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## 예제  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## 예제  
 이 샘플에서는 숫자 계산의 결과를 포함하는 데 사용되는 형식을 확인하기 위해 <xref:System.Object.GetType%2A> 메서드를 사용합니다.  이 형식은 계산 결과를 저장하는 데 필요한 요구 사항에 따라 달라집니다.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Type?displayProperty=fullName>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)