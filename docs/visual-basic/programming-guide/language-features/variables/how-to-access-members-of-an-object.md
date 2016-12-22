---
title: "How to: Access Members of an Object (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "members, accessing"
  - "object variables, accessing members"
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Access Members of an Object (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

개체를 참조하는 개체 변수가 있을 때 해당 개체의 메서드, 속성, 필드 및 이벤트 같은 개체 멤버를 사용해야 하는 경우가 종종 있습니다.  예를 들어, 새 <xref:System.Windows.Forms.Form> 개체를 만든 후 이 개체의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 설정하거나 <xref:System.Windows.Forms.Control.Focus%2A> 메서드를 호출해야 하는 경우가 있습니다.  
  
## 멤버에 액세스  
 개체를 참조하는 변수를 통해 개체 멤버에 액세스할 수 있습니다.  
  
#### 개체의 멤버에 액세스하려면  
  
-   개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자\(`.`\)를 사용합니다.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     멤버가 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 멤버이면 변수 없이도 개체에 액세스할 수 있습니다.  
  
## 알려진 형식의 개체 멤버에 액세스  
 컴파일 타임에 개체 형식을 알면 개체를 참조하는 변수에 대해 *초기 바인딩*을 사용할 수 있습니다.  
  
#### 컴파일 타임에 알려진 형식의 개체 멤버에 액세스하려면  
  
1.  개체 변수를 변수에 할당하려는 개체의 형식으로 선언합니다.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form   
    ```  
  
     `Option Strict On`을 사용하면 <xref:System.Windows.Forms.Form> 개체 또는 <xref:System.Windows.Forms.Form>에서 파생된 형식의 개체만 `extraForm`에 할당할 수 있습니다.  <xref:System.Windows.Forms.Form>으로 `CType` 확대 변환을 수행하여 클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체를 `extraForm`에 할당할 수도 있습니다.  
  
2.  개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자\(`.`\)를 사용합니다.  
  
    ```  
    extraForm.Show()  
    ```  
  
     `Option Strict` 설정에 관계없이 <xref:System.Windows.Forms.Form> 클래스와 관련된 모든 메서드 및 속성에 액세스할 수 있습니다.  
  
## 알려지지 않은 형식의 개체 멤버에 액세스  
 컴파일 타임에 개체 형식을 모르면 개체를 참조하는 모든 변수에 대해 *런타임에 바인딩*을 사용해야 합니다.  
  
#### 컴파일 타임에 알려지지 않은 형식의 개체 멤버에 액세스하려면  
  
1.  개체 변수를 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)으로 선언합니다.  변수를 `Object`로 선언하는 것은 변수를 <xref:System.Object?displayProperty=fullName>로 선언하는 것과 같습니다.  
  
    ```  
    Dim someControl As Object   
    ```  
  
     `Option Strict On`을 사용하면 <xref:System.Object> 클래스에 정의된 멤버에만 액세스할 수 있습니다.  
  
2.  개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자\(`.`\)를 사용합니다.  
  
    ```  
    someControl.GetType()  
    ```  
  
     개체 변수에 할당하는 모든 개체의 멤버에 액세스할 수 있도록 하려면 `Option Strict Off`를 설정해야 합니다.  이 경우 컴파일러에서 해당 멤버는 변수에 할당된 개체를 사용하지 않고도 노출될 수 있습니다.  액세스하려는 멤버를 개체에서 노출하지 않으면 <xref:System.MemberAccessException> 예외가 발생합니다.  
  
## 참고 항목  
 <xref:System.Object>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.MemberAccessException>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)