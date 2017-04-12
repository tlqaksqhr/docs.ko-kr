---
title: "Me, My, MyBase 및 MyClass Visual Basic의 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 59dba8961712537367db9a60e8b8ba68bcb6a1ea
ms.lasthandoff: 03/13/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic의 Me, My, MyBase 및 MyClass
`Me``My`, `MyBase`, 및 `MyClass` 에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 유사한 이름에 있지만 서로 다른 목적으로 합니다. 이 항목에서는 구별할 수 있도록 이러한 각 엔터티를 설명 합니다.  
  
## <a name="me"></a>Me  
 `Me` 키워드는 클래스 또는 구조체는 코드가 현재 실행 중인의 특정 인스턴스를 참조 하는 방법을 제공 합니다. `Me`현재 인스턴스 참조 구조 변수 또는 개체 변수 처럼 동작 합니다. 사용 하 여 `Me` 프로시저 다른 클래스, 구조체 또는 모듈에는 클래스 또는 구조체의 현재 실행 중인 인스턴스에 대 한 정보를 전달 하는 데 특히 유용 합니다.  
  
 예를 들어, 모듈에서 다음 절차를 사용 해야 합니다.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 이 프로시저를 호출 하 고의 현재 인스턴스를 전달할 수는 <xref:System.Windows.Forms.Form>클래스는 다음 문을 사용 하 여 인수로.</xref:System.Windows.Forms.Form>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 `My` 수의 쉽고 직관적인 액세스를 제공 하는 기능 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 클래스에는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴퓨터, 응용 프로그램, 설정, 리소스 및 등과 상호 작용 하는 사용자입니다.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` 키워드는 클래스의 현재 인스턴스는 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다. `MyBase`일반적으로 재정의 되거나 파생된 클래스에서 숨겨진 하는 기본 클래스 멤버에 액세스 하는 데 사용 됩니다. `MyBase.New`파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 작동 합니다. `MyClass`비슷합니다 `Me`, 모든 메서드 호출에는 해당 메서드가 것 처럼 처리 됩니다 하지만 `NotOverridable`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
