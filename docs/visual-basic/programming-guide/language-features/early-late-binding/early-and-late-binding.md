---
title: "Early and Late Binding (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
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
  - "early binding"
  - "objects [Visual Basic], late-bound"
  - "objects [Visual Basic], early-bound"
  - "objects [Visual Basic], late bound"
  - "early binding, Visual Basic compiler"
  - "binding, late and early"
  - "objects [Visual Basic], early bound"
  - "Visual Basic compiler, early and late binding"
  - "late binding"
  - "late binding, Visual Basic compiler"
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Early and Late Binding (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 개체가 개체 변수에 할당될 때 `binding`이라는 프로세스를 수행합니다.  개체가 특정 개체 형식으로 선언된 변수에 할당되면 *초기 바인딩*되었다고 합니다.  초기 바인딩 개체를 사용하면 응용 프로그램이 실행되기 전에 컴파일러에서 메모리를 할당하고 다른 최적화 작업을 수행합니다.  예를 들어, 다음 코드 조각에서는 변수를 <xref:System.IO.FileStream> 형식으로 선언합니다.  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#90)]  
  
 <xref:System.IO.FileStream>은 특정 개체 형식이므로 `FS`에 할당된 인스턴스는 초기에 바인딩됩니다.  
  
 이와는 반대로 개체가 `Object` 형식으로 선언된 변수에 할당되면 *런타임에 바인딩*되었다고 합니다.  이러한 형식의 개체에는 임의의 개체에 대한 참조가 포함될 수 있지만 초기 바인딩된 개체가 제공하는 여러 가지 이점을 제공하지는 않습니다.  예를 들어, 다음 코드 조각에서는 `CreateObject` 함수에서 반환된 개체를 포함하는 개체 변수를 선언합니다.  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/LateBinding.vb#91)]  
  
## 초기 바인딩의 장점  
 초기 바인딩 개체를 사용하면 컴파일러에서 중요한 최적화 작업이 수행되어 보다 효율적인 응용 프로그램을 만들 수 있습니다.  초기 바인딩 개체는 런타임에 바인딩된 개체보다 훨씬 빠르기 때문에 정확하게 사용되는 개체가 어떤 종류인지 보여 줌으로써 코드가 유지 관리되고 코드의 가독성이 향상됩니다.  뿐만 아니라 초기 바인딩을 사용하면 [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] IDE\(통합 개발 환경\)에서 코드를 편집할 때 작업하는 개체의 형식을 정확하게 파악할 수 있으므로 자동 코드 완성 및 동적 도움말과 같은 유용한 기능을 사용할 수 있습니다.  초기 바인딩을 사용하면 프로그램이 컴파일될 때 컴파일러에서 오류를 보고할 수 있으므로 런타임 오류의 수와 심각성을 줄일 수 있습니다.  
  
> [!NOTE]
>  런타임에 바인딩은 `Public`으로 선언된 형식 멤버에 액세스할 때만 사용할 수 있습니다.  `Friend`나 `Protected Friend`로 선언된 멤버에 액세스하면 런타임 오류가 발생합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)