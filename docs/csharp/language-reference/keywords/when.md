---
title: "when(C# 참조)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ae869fa04d2dfb963694f258624c5cd594ff1184
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
 # <a name="when-c-reference"></a>when(C# 참조)

`when` 상황별 키워드를 사용하여 두 가지 상황에서 필터 조건을 지정할 수 있습니다.

- [try/catch](try-catch.md) 또는 [try/catch/finally](try-catch-finally.md) 블록의 `catch` 문에서
- [switch](switch.md) 문의 `case` 레이블에서

## <a name="when-in-a-catch-statement"></a>`catch` 문의 `when`

C# 6부터, 특정 예외에 대한 처리기를 실행하기 위해 참이 되어야 하는 조건을 지정하기 위해 `catch` 문에서 `When`을 사용할 수 있습니다. 사용되는 구문은 다음과 같습니다.

```csharp
catch ExceptionType [e] when (expr)
```
여기서 *expr*은 부울 값으로 계산되는 식입니다. `true`가 반환되면 예외 처리기가 실행되고, `false`가 반환되면 실행되지 않습니다. 

다음 예제는 `when` 키워드를 사용하여 예외 메시지의 텍스트에 따라 @System.Net.HttpRequestException에 대한 처리기를 조건부로 실행합니다.

 [!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`switch` 문의 `when`

7부터 `case` 레이블은 더 이상 상호 배타적일 필요가 없으며 `case` 레이블이 `switch` 문에 나타나는 순서로 어떤 스위치 블록을 실행할지를 결정할 수 있습니다. 필터 조건도 참인 경우에만 관련 사례 레이블을 참으로 만드는 필터 조건을 지정하려면 `when` 키워드를 사용할 수 있습니다. 사용되는 구문은 다음과 같습니다.

```csharp
case (expr) where (when-condition):
```
여기서 *expr*은 일치 식과 비교되는 상수 패턴 또는 형식 패턴이며 *when-condition*은 부울 식입니다. 

다음 예제에서는 `when` 키워드를 사용하여 영역이 0인 `Shape` 개체를 테스트하고 영역이 0보다 큰 다양한 `Shape` 개체를 테스트합니다. 

 [!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>참고 항목 
  [switch 문](switch.md)  
  [try/catch 문](try-catch.md)  
  [try/catch/finally 문](try-catch-finally.md) 


