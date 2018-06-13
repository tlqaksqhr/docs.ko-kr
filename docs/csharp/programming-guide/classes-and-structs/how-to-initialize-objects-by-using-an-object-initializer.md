---
title: '방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 1f5f068cd8dc3787eb8cb2cd72cc30e9ea159390
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320910"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>방법: 개체 이니셜라이저를 사용하여 개체 초기화(C# 프로그래밍 가이드)
개체 이니셜라이저를 사용하여 형식에 대한 생성자를 명시적으로 호출하지 않고 선언적 방식으로 형식 개체를 초기화할 수 있습니다.  
  
 다음 예제에서는 명명된 개체와 함께 개체 이니셜라이저를 사용하는 방법을 보여 줍니다. 컴파일러는 먼저 기본 인스턴스 생성자에 액세스한 다음 멤버 초기화를 처리하여 개체 이니셜라이저를 처리합니다. 따라서 클래스에서 기본 생성자가 `private`로 선언된 경우 공용 액세스가 필요한 개체 이니셜라이저는 실패합니다.  
  
 무명 형식을 정의하는 경우 개체 이니셜라이저를 사용해야 합니다. 자세한 내용은 [방법: 쿼리에서 요소 속성의 하위 집합 반환](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 예제에서는 개체 이니셜라이저를 사용하여 새 `StudentName` 형식을 초기화하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a>예  
 다음 예제에서는 컬렉션 이니셜라이저를 사용하여 `StudentName` 형식 컬렉션을 초기화하는 방법을 보여 줍니다. 컬렉션 이니셜라이저는 일련의 쉼표로 구분된 개체 이니셜라이저입니다.  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 실행하려면 클래스를 복사하여 Visual Studio에서 만든 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [개체 이니셜라이저 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
