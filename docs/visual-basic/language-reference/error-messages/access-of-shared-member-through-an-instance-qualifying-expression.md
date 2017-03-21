---
title: "인스턴스;를 통한 공유 멤버 액세스 정규화 식을 계산 하지 것입니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
dev_langs:
- VB
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39be3c95d5acc20afe3a33be9d4db48c09f99a9c
ms.lasthandoff: 03/13/2017

---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>인스턴스를 통한 공유 멤버 액세스입니다. 정규화 식을 계산하지 않습니다.
클래스 또는 구조체의 인스턴스 변수를 사용 하는 사용 되는 액세스 하는 `Shared` 변수, 속성, 프로시저 또는 해당 클래스 또는 구조체에 정의 된 이벤트입니다. 이 경고는 클래스 또는 상수 또는 열거형 또는 중첩 된 클래스 또는 구조체와 같은 구조체의 암시적으로 공유 된 멤버에 액세스 하는 인스턴스 변수를 사용 하는 경우에 발생할 수 있습니다.  
  
 공유 멤버의 목적은를 해당 멤버의 단일 복사본만 만들고 단일 복사본을 확인 하는 클래스 또는 선언 된 구조체의 모든 인스턴스에서 사용할 수 있습니다. 이러한 목적을 위해 액세스 하는 것과 일관성이 `Shared` 해당 클래스 또는 구조체의 개별 인스턴스를 보유 하는 변수 대신 해당 클래스 또는 구조체의 이름을 통해 멤버입니다.  
  
 에 액세스 하는 `Shared` 인스턴스 변수를 통해 멤버는 멤버는 모호 이해 하기 어려울 코드를 만들 수 `Shared`합니다. 또한 이러한 액세스 식의 일부인 경우 다른 작업을 수행 하와 같은 한 `Function` 공유 멤버의 인스턴스를 반환 하는 프로시저 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 식 및 수행할 수도 있는 모든 작업을 건너뜁니다.  
  
 자세한 내용 및 예제에 대 한 참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   클래스 또는 구조체 정의 하는 이름을 사용 하는 `Shared` 멤버는 다음 예와에서 같이 액세스할 수 있습니다.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  두 프로그래밍 요소에 동일한 이름을 사용할 경우 범위의 영향에 대 한 경고 수입니다. 이전 예제를 사용 하 여 인스턴스를 선언 하는 경우 `Dim testClass as testClass = Nothing`, 컴파일러에 대 한 호출을 처리 `testClass.sayHello()` 클래스 이름 및 경고 메시지를 통해 메서드에 대 한 액세스를 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Visual Basic의 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
