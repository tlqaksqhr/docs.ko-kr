---
title: "동적 개체 (Visual Basic) 작업 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
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
ms.openlocfilehash: 366b563764baaa39849356a782ecee264b2ae94f
ms.lasthandoff: 03/13/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a>동적 개체 작업(Visual Basic)
동적 개체는 또 다른 방법은 이외의 제공는 `Object` 에 런타임에 개체에 바인딩할 형식입니다. 동적 개체에 정의 된 동적 인터페이스를 사용 하 여 런타임에 속성 및 메서드 같은 멤버를 노출 된 <xref:System.Dynamic>네임 스페이스.</xref:System.Dynamic> 클래스를 사용할 수는 <xref:System.Dynamic>정적 형식 또는 형식 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들 네임 스페이스.</xref:System.Dynamic> IronPython 및 IronRuby와 같은 동적 언어에 정의 된 동적 개체를 사용할 수 있습니다. 동적 개체를 만들거나 동적 언어에 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제를 보려면 [연습: 동적 개체 만들기 및 사용 하 여](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, 또는 <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]동적 언어 런타임 및 IronPython 및 IronRuby와 같은 동적 언어에서 사용 하 여 개체에 바인딩하는 <xref:System.Dynamic.IDynamicMetaObjectProvider>인터페이스.</xref:System.Dynamic.IDynamicMetaObjectProvider> 구현 하는 클래스의 예는 `IDynamicMetaObjectProvider` 인터페이스는는 <xref:System.Dynamic.DynamicObject>및 <xref:System.Dynamic.ExpandoObject>클래스.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 런타임에 바인딩된 호출 하려고 구현 하는 개체는 `IDynamicMetaObjectProvider` 인터페이스를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 해당 인터페이스를 사용 하 여 동적 개체에 바인딩합니다. 구현 하지 않는 개체에 런타임에 바인딩된 호출 하는 경우는 `IDynamicMetaObjectProvider` 인터페이스, 경우에 대 한 호출은 `IDynamicMetaObjectProvider` 실패 하면 인터페이스 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 의 런타임 바인딩 기능을 사용 하 여 개체에 바인딩합니다는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 런타임입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject>   
 [연습: 동적 개체를 사용 하 여 만들고](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
