---
title: "Working with Dynamic Objects (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "dynamic objects [Visual Basic]"
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Working with Dynamic Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

동적 개체는 런타임에 개체에 바인딩할 수 있는 방법으로 `Object` 형식 대신 사용됩니다.  동적 개체는 <xref:System.Dynamic> 네임스페이스에 정의되어 있는 동적 인터페이스를 사용하여 속성 및 메서드 같은 멤버를 런타임에 노출합니다.  <xref:System.Dynamic> 네임스페이스의 클래스를 사용하면 정적 형식 또는 포맷과 일치하지 않는 데이터 구조를 처리하는 개체를 만들 수 있습니다.  또한 IronPython 및 IronRuby 같은 동적 언어로 정의된 동적 개체도 사용할 수 있습니다.  동적 개체를 만들거나 동적 언어로 정의된 동적 개체를 사용하는 방법은 [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> 또는 <xref:System.Dynamic.ExpandoObject>를 참조하십시오.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스를 사용하여 IronPython 및 IronRuby 같은 동적 언어 및 동적 언어 런타임의 개체에 바인딩합니다.  `IDynamicMetaObjectProvider` 인터페이스를 구현하는 클래스로는 <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject> 클래스가 있습니다.  
  
 `IDynamicMetaObjectProvider` 인터페이스를 구현한 개체에 런타임에 바인딩되는 호출을 사용하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 이 인터페이스를 사용하여 동적 개체에 바인딩합니다.  `IDynamicMetaObjectProvider` 인터페이스를 구현하지 않은 개체에 런타임에 바인딩되는 호출을 사용하거나 `IDynamicMetaObjectProvider` 인터페이스에 대한 호출이 실패한 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 런타임에 바인딩하는 기능을 사용하여 해당 개체에 바인딩합니다.  
  
## 참고 항목  
 <xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject>   
 [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)