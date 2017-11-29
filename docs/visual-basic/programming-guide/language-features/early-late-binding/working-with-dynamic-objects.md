---
title: "동적 개체 작업(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a>동적 개체 작업(Visual Basic)
동적 개체는 또 다른 방법은 이외의 `Object` 에 바인딩할 수 있는 개체 런타임 시 형식입니다. 동적 개체에 정의 된 동적 인터페이스를 사용 하 여 런타임 시 속성 및 메서드와 같은 멤버를 노출 된 <xref:System.Dynamic> 네임 스페이스입니다. 클래스를 사용할 수는 <xref:System.Dynamic> 정적 유형 또는 응답 형식이 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들려는 네임 스페이스입니다. IronPython 및 IronRuby과 같은 동적 언어에서 정의 된 동적 개체를 사용할 수 있습니다. 동적 개체를 만들거나 동적 언어로 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제를 보려면 [연습: 동적 개체 만들기 및 사용 하 여](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, 또는 <xref:System.Dynamic.ExpandoObject>합니다.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]동적 언어 런타임 및 IronPython 및 IronRuby과 같은 동적 언어에서 사용 하 여 개체에 바인딩합니다는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스입니다. 구현 하는 클래스의 예는 `IDynamicMetaObjectProvider` 인터페이스는 <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject> 클래스입니다.  
  
 구현 하는 개체는 런타임에 바인딩된 호출 된 경우는 `IDynamicMetaObjectProvider` 인터페이스 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 해당 인터페이스를 사용 하 여 동적 개체에 바인딩합니다. 런타임에 바인딩된 호출을 구현 하지 않는 개체에 만들어질 경우는 `IDynamicMetaObjectProvider` 인터페이스를 경우에 대 한 호출에서 `IDynamicMetaObjectProvider` 실패 인터페이스 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 런타임에 바인딩 기능을 사용 하 여 개체에 바인딩합니다는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 런타임.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
