---
title: "Nothing (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Nothing"
  - "vb.Nothing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing keyword"
  - "Nothing keyword, syntax"
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: 31
caps.handback.revision: 31
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Nothing (Visual Basic)
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

모든 데이터 형식의 기본값을 나타냅니다.  기본값은 참조 형식에 대 한 것은 `null` 참조.  값 형식에 대 한 기본값의 값 형식은 null 허용 여부에 따라 달라 집니다.  
  
> [!NOTE]
>  Nullable이 아닌 값 형식에 대 한 `Nothing` Visual Basic 다른 `null` C\#에 있습니다.  Visual Basic에는 nullable이 아닌 값 형식의 변수를 설정 하는 경우 `Nothing`, 변수 선언 된 형식에 대해 기본값으로 설정 됩니다.  에 C\#에 nullable이 아닌 값 형식의 변수를 할당 하는 경우, `null`, 컴파일 타임 오류가 발생 합니다.  
  
## 설명  
 `Nothing`데이터 형식의 기본값을 나타냅니다.  기본값은 변수에 값 형식 또는 참조 형식 인지에 따라 달라 집니다.  
  
 변수는  *값 형식* 직접 해당 값을 포함 합니다.  모든 숫자 데이터 형식, 값 형식 등이 `Boolean`, `Char`, `Date`, 모든 구조 및 모든 열거형입니다.  변수는  *참조 형식* 개체의 인스턴스에 대 한 참조를 메모리에 저장 합니다.  참조 형식은 클래스, 배열, 대리자 및 문자열을 포함합니다.  자세한 내용은 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)를 참조하십시오.  
  
 변수 값이 있으면 입력, 동작을 `Nothing` 변수는 null 허용 데이터 형식 인지 여부에 따라 달라 집니다.  Nullable 값 형식을 나타내는 추가 된 `?` 형식 이름에 한정자입니다.  할당 `Nothing` 에 null 허용 변수 값을 설정 `null`.  자세한 내용과 예제를 보려면 [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)을 참조하십시오.  
  
 Nullable이 아닌 값 형식의 변수인 경우 할당 `Nothing` 하 여 기본 값으로 선언 된 형식에 대 한 설정입니다.  해당 형식이 변수 멤버를 포함하면 변수 멤버도 모두 기본값으로 설정합니다.  다음 예제에서는 스칼라 형식에 대한 이 작업을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 변수가 참조 형식인 경우 할당 `Nothing` 변수를 설정는 `null` 참조 변수 형식입니다.  설정 되는 변수는 `null` 참조 개체와 관련 된 수 없습니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 변수는 참조 \(또는 nullable 값 입력 여부\) 확인할 때 `null`를 사용 하지 않는 `= Nothing` 또는 `<> Nothing`.  Always use `Is Nothing` or `IsNot Nothing`.  
  
 Visual Basic 문자열에 대 한 빈 문자열에 해당 `Nothing`.  따라서, `"" = Nothing` 마찬가지입니다.  
  
 다음 예제에서는 `Is` 및 `IsNot` 연산자를 사용하는 비교를 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 `As` 절을 사용하지 않고 변수를 선언하고 해당 변수를 `Nothing`으로 설정하면 변수의 형식은 `Object`입니다.  이 예제는 `Dim something = Nothing`입니다.  이 경우 컴파일 타임 오류가 발생 하면 `Option Strict` 설정 되어 및 `Option Infer` 꺼져 있습니다.  
  
 `Nothing`을 개체 변수에 할당하면 개체 변수가 더 이상 개체 인스턴스를 참조하지 않습니다.  변수가 이전에 인스턴스를 참조한 경우 `Nothing`으로 설정하면 인스턴스 자체는 종료되지 않습니다.  GC\(가비지 수집기\)가 남아 있는 활성 참조가 없음을 발견한 후에만 인스턴스가 종료되고 인스턴스와 관련된 메모리 및 시스템 리소스가 해제됩니다.  
  
 `Nothing`다릅니다는 <xref:System.DBNull> 는 초기화 되지 않은 variant 또는 존재 하지 않는 데이터베이스 열을 나타내는 개체입니다.  
  
## 참고 항목  
 [Dim Statement](../../visual-basic/language-reference/statements/dim-statement.md)   
 [Object Lifetime: How Objects Are Created and Destroyed](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Lifetime in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Is Operator](../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)