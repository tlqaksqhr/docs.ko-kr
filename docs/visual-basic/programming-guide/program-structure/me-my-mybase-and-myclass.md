---
title: "Me, My, MyBase, and MyClass in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MyClass"
  - "vb.Me"
  - "MyBase"
  - "vb.MyBase"
  - "Me"
  - "vb.MyClass"
  - "vb.This"
  - "vb.My"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My object"
  - "self-reference, Me keyword"
  - "MyClass keyword, relationship to similar programming elements"
  - "Me keyword, relationship to similar programming elements"
  - "Me keyword, referring to the current instance of an object"
  - "Me keyword"
  - "self-reference"
  - "current instance, Me keyword"
  - "MyBase keyword, relationship to similar programming elements"
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Me, My, MyBase, and MyClass in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 `Me`, `My`, `MyBase` 및 `MyClass`는 이름이 비슷하지만 용도가 다릅니다.  이 항목에서는 이러한 엔터티를 구별할 수 있도록 각 엔터티에 대해 설명합니다.  
  
## Me  
 `Me` 키워드를 사용하면 코드에서 현재 실행하고 있는 클래스 또는 구조체의 특정 인스턴스를 참조할 수 있습니다.  `Me`는 현재 인스턴스를 참조하는 개체 변수나 구조체 변수처럼 동작합니다.  다른 클래스, 구조체 또는 모듈의 프로시저에 현재 실행 중인 클래스나 구조체의 인스턴스에 대한 정보를 전달할 때 `Me`를 사용하면 특히 유용합니다.  
  
 예를 들어, 모듈에 다음 프로시저가 있다고 가정합니다.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 이 프로시저를 호출한 다음 아래 문을 사용하여 <xref:System.Windows.Forms.Form> 클래스의 현재 인스턴스를 인수로 전달할 수 있습니다.  
  
```  
ChangeFormColor(Me)  
```  
  
## My  
 `My` 기능을 사용하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 사용자가 컴퓨터, 응용 프로그램, 설정, 리소스 등과 상호 작용할 수 있는 다양한 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스에 쉽게 액세스할 수 있습니다.  
  
## MyBase  
 `MyBase` 키워드는 현재 클래스 인스턴스의 기본 클래스를 참조하는 개체 변수처럼 동작합니다.  `MyBase`는 파생 클래스에서 재정의되거나 숨겨진 기본 클래스 멤버에 액세스하는 데 주로 사용됩니다.  `MyBase.New`는 파생 클래스 생성자에서 명시적으로 기본 클래스 생성자를 호출하는 데 사용됩니다.  
  
## MyClass  
 `MyClass` 키워드는 원래 구현된 상태의 현재 클래스 인스턴스를 참조하는 개체 변수처럼 동작합니다.  `MyClass`는 `Me`와 유사하지만 MyClass의 모든 메서드 호출은 해당 메서드가 `NotOverridable`인 것처럼 처리됩니다.  
  
## 참고 항목  
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)