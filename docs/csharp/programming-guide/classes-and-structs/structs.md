---
title: 구조체(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="structs-c-programming-guide"></a>구조체(C# 프로그래밍 가이드)
구조체는 [struct](../../../csharp/language-reference/keywords/struct.md) 키워드를 사용하여 정의합니다. 예를 들면 다음과 같습니다.  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 구조체가 클래스보다 더 제한적이지만 구조체는 클래스와 동일한 구문을 대부분 공유합니다.  
  
-   구조체 선언 내에서 필드가 const 또는 static으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.  
  
-   구조체는 기본 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.  
  
-   할당 시 구조체가 복사됩니다. 구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다. Dictionary\<string, myStruct> 등의 값 형식 컬렉션으로 작업하는 경우 이 점을 명심해야 합니다.  
  
-   구조체는 값 형식이고 클래스는 참조 형식입니다.  
  
-   클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.  
  
-   구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.  
  
-   구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다. 모든 구조체는 `System.Object`에서 상속하는 `System.ValueType`에서 직접 상속합니다.  
  
-   구조체는 인터페이스를 구현할 수 있습니다.  
  
-   구조체는 nullable 형식으로 사용할 수 있으며 null 값을 할당할 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [구조체 사용](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [방법: 메서드에 구조체를 전달하는 것과 클래스 참조를 전달하는 것의 차이점 이해](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)
