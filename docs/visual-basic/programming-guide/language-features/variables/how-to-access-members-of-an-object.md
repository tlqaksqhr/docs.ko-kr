---
title: "방법: 개체의 멤버에 액세스(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 85fa4932b449bf7b9ecb3902fc17fd954ea8cfac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>방법: 개체의 멤버에 액세스(Visual Basic)
개체를 참조 하는 개체 변수를 설정한 경우 종종 메서드, 속성, 필드, 이벤트 등 해당 개체의 멤버를 사용 하려고 합니다. 예를 들어 만든 후 새 <xref:System.Windows.Forms.Form> 개체를 설정 하려는 경우 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성 또는 호출의 <xref:System.Windows.Forms.Control.Focus%2A> 메서드.  
  
## <a name="accessing-members"></a>멤버 액세스  
 참조 하는 변수를 통해 개체의 멤버에 액세스 합니다.  
  
#### <a name="to-access-members-of-an-object"></a>개체의 멤버에 액세스  
  
-   멤버 액세스 연산자를 사용 하 여 (`.`) 사이의 개체 변수 이름 및 멤버 이름입니다.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     멤버인 경우 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), 변수를 액세스할 필요가 없습니다.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>알려진 형식의 개체의 멤버에 액세스  
 사용할 수 있습니다 컴파일 타임에 개체의 형식을 알고 있는 경우 *초기 바인딩* 참조 하는 변수에 대 한 합니다.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>컴파일 타임에 형식을 알고 있는 개체의 멤버에 액세스  
  
1.  개체 변수를 변수에 할당할 개체 유형으로 선언 합니다.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     와 `Option Strict On`만 할당할 수 있습니다 <xref:System.Windows.Forms.Form> 개체 (또는에서 파생 된 형식의 개체가 <xref:System.Windows.Forms.Form>)를 `extraForm`합니다. 클래스 또는 구조체는 확대 정의한 경우 `CType` 변환할 <xref:System.Windows.Forms.Form>, 할당할 해당 클래스 또는 구조체를 수도 있습니다 `extraForm`합니다.  
  
2.  멤버 액세스 연산자를 사용 하 여 (`.`) 사이의 개체 변수 이름 및 멤버 이름입니다.  
  
    ```  
    extraForm.Show()  
    ```  
  
     모든 메서드 및 속성에만 액세스할 수 있습니다는 <xref:System.Windows.Forms.Form> 관계 없이 클래스는 `Option Strict` 설정은입니다.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>알 수 없는 형식의 개체의 멤버에 액세스  
 컴파일 타임에 개체의 형식을 알지 못하는 경우 사용 해야 *런타임에 바인딩* 참조 하는 모든 변수에 대해 합니다.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>알지 못하는 유형을 컴파일 타임에 개체의 멤버에 액세스  
  
1.  개체 변수를 선언 된 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다. (로 변수 선언 `Object` 로 선언 하는 것과 같습니다 <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     와 `Option Strict On`에 정의 된 멤버에만 액세스할 수 있습니다는 <xref:System.Object> 클래스입니다.  
  
2.  멤버 액세스 연산자를 사용 하 여 (`.`) 사이의 개체 변수 이름 및 멤버 이름입니다.  
  
    ```  
    someControl.GetType()  
    ```  
  
     설정 해야 개체 변수에 할당 하는 모든 개체의 멤버에 액세스할 수 있으려면 `Option Strict Off`합니다. 이 작업을 수행 하는 경우 컴파일러는 변수에 할당할 개체에 의해 지정된 된 멤버 노출 된다는 것을 보장할 수 없습니다. 개체에 액세스 하려는 멤버를 노출 하지 않습니다 하는 경우는 <xref:System.MemberAccessException> 예외가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
