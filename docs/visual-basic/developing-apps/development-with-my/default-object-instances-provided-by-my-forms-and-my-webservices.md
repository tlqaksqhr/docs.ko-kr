---
title: "Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.WebServices object, developing applications"
  - "My.Forms object, developing applications"
  - "rapid application development (RAD), My.Forms"
  - "rapid application development (RAD), My.WebServices"
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) 및 [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) 개체는 응용 프로그램에서 사용하는 XML Web services, 데이터 소스 및 폼에 대한 액세스 권한을 제공합니다.  이때 이러한 개체는 각각의 *기본 인스턴스* 콜렉션을 제공합니다.  
  
## 기본 인스턴스  
 기본 인스턴스는 런타임에서 제공하는 클래스의 인스턴스로서, `Dim` 및 `New` 문을 사용하여 선언하거나 인스턴스화하지 않아도 됩니다.  다음 예제에서는 `Form1` <xref:System.Windows.Forms.Form> 클래스의 인스턴스를 선언하고 인스턴스화한 방법과 `My.Forms`를 통해 이 <xref:System.Windows.Forms.Form> 클래스의 기본 인스턴스를 가져올 수 있는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/default-object-instances_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/default-object-instances_2.vb)]  
  
 `My.Forms` 개체는 프로젝트에 있는 모든 `Form` 클래스의 기본 인스턴스 콜렉션을 반환합니다.  마찬가지로 `My.WebServices`는 사용자가 해당 응용 프로그램에서 참조를 만든 모든 웹 서비스에 대한 프록시 클래스의 기본 인스턴스를 제공합니다.  
  
## 참고 항목  
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)