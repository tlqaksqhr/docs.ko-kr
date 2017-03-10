---
title: "방법: 문자열 내용 수정(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열[C#], 수정"
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# 방법: 문자열 내용 수정(C# 프로그래밍 가이드)
문자열은 *변경 불가능*하므로 문자열 개체를 만든 후에 안전하지 않은 코드를 사용하지 않고 문자열 개체의 값을 수정할 수는 없습니다.  하지만 문자열 값을 수정하여 그 결과를 새 문자열 개체에 저장하는 방법은 많습니다.  <xref:System.String?displayProperty=fullName> 클래스는 입력 문자열을 처리하여 새 문자열 개체를 반환하는 메서드를 제공합니다.  많은 경우 새 개체를 원래 문자열을 유지하는 변수에 할당할 수 있습니다.  <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 클래스는 유사한 방식으로 작동하는 추가 메서드를 제공합니다.  <xref:System.Text.StringBuilder?displayProperty=fullName> 클래스는 "내부"에서 수정할 수 있는 문자 버퍼를 제공합니다. <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> 메서드를 호출하여 버퍼의 현재 내용을 포함하는 새 문자열 개체를 만들 수 있습니다.  
  
## 예제  
 다음 예제에서는 지정된 문자열에서 부분 문자열을 바꾸거나 제거하는 다양한 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#28)]  
  
## 예제  
 배열 표기법을 사용하여 문자열의 개별 문자에 액세스하려면 <xref:System.Text.StringBuilder> 개체를 사용합니다. 이 개체를 사용하면 `[]` 연산자를 오버로드하여 개체의 내부 문자 버퍼에 액세스할 수 있습니다.  <xref:System.String.ToCharArray%2A> 메서드를 사용하면 문자열을 문자 배열로 변환할 수도 있습니다.  다음 예제에서는 `ToCharArray`를 사용하여 배열을 만듭니다.  그런 다음 이 배열의 요소 일부를 수정합니다.  계속해서, 문자 배열을 입력 매개 변수로 사용하는 문자열 생성자가 호출되어 새 문자열이 만들어집니다.  
  
 [!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#24)]  
  
## 예제  
 다음 예제에서는 C 스타일의 문자 배열과 유사한 방식으로 안전하지 않은 코드를 사용하여 문자열을 내부적으로 수정해야 하는 매우 드문 경우를 보여 줍니다.  이 예제에서는 fixed 키워드를 사용하여 개별 문자에 "내부적으로" 액세스하는 방법을 보여 줍니다.  또한 C\# 컴파일러가 내부적으로 문자열을 저장하는 방식 때문에 문자열에 대한 안전하지 않은 작업에서 발생할 수 있는 부작용에 대해서도 설명합니다.  일반적으로 반드시 필요한 경우가 아니라면 이 방법을 사용해서는 안 됩니다.  
  
 [!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#29)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)