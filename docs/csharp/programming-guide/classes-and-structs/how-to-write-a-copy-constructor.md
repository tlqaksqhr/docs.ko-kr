---
title: "방법: 복사 생성자 작성(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f15d8fabc49cbff5515b78a7d2fb6f9e49d0704e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>방법: 복사 생성자 작성(C# 프로그래밍 가이드)
C#에서는 개체에 대한 복사 생성자를 제공하지 않지만 직접 작성할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 `Person`[클래스](../../../csharp/language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다. 인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다. 코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ICloneable>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)
