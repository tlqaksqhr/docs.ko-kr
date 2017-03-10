---
title: "구조체(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 구조체"
  - "구조체[C#]"
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# 구조체(C# 프로그래밍 가이드)
구조체는 다음 예제와 같이 [struct](../../../csharp/language-reference/keywords/struct.md) 키워드를 사용하여 정의합니다.  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/structs_1.cs)]  
  
 구조체는 클래스와 동일한 구문을 대부분 공유하지만 클래스보다 제한적입니다.  
  
-   구조체 선언 내에서 필드는 const 또는 static으로 선언한 경우에만 초기화할 수 있습니다.  
  
-   구조체에서는 매개 변수가 없는 생성자인 기본 생성자나 소멸자를 선언할 수 없습니다.  
  
-   구조체는 할당 시 복사됩니다.  구조체가 새 변수에 할당되면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다.  Dictionary\<string, myStruct\>와 같은 값 형식의 컬렉션을 사용할 때 이것이 중요합니다.  
  
-   구조체는 값 형식이고 클래스는 참조 형식입니다.  
  
-   클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.  
  
-   구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.  
  
-   구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.  모든 구조체는 `System.Object`를 상속하는 `System.ValueType`에서 직접 상속합니다.  
  
-   구조체는 인터페이스를 구현할 수 있습니다.  
  
-   구조체를 nullable 형식으로 사용할 수 있고 여기에 null 값을 할당할 수 있습니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [방법: 메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점 이해](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [변수에 대 한 자세한](란?LinkId%20=%20221230) 에서 [처음 Visual C\# 2010](란?LinkId%20=%20221214)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)