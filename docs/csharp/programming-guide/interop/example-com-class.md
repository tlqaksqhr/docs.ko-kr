---
title: "COM 클래스 예제(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "COM, Visual C# 개체 노출"
  - "예제[C#], COM 클래스"
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# COM 클래스 예제(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음은 COM 개체로 노출되는 클래스의 예제입니다.  이 코드를 .cs 파일에 포함시켜 프로젝트에 추가한 다음 **COM Interop 등록** 속성을 **True**로 설정합니다.  자세한 내용은 [NIB: How to: Register a Component for COM Interop](http://msdn.microsoft.com/ko-kr/4de7d474-56e8-4027-994d-d47ca4725c5e)을 참조하십시오.  
  
 Visual C\# 개체를 COM에 노출시키려면 클래스 인터페이스와 클래스 자체를 선언하고 필요하면 이벤트 인터페이스도 선언해야 합니다.  클래스 멤버는 다음 규칙을 따르는 경우에만 COM에 노출됩니다.  
  
-   클래스가 public이어야 합니다.  
  
-   속성, 메서드 및 이벤트가 public이어야 합니다.  
  
-   클래스 인터페이스에 속성 및 메서드가 선언되어 있어야 합니다.  
  
-   이벤트 인터페이스에 이벤트가 선언되어 있어야 합니다.  
  
 이 인터페이스에서 선언되지 않은 클래스의 다른 public 멤버는 COM에 노출되지 않지만 다른 .NET Framework 개체에는 노출됩니다.  
  
 속성 및 메서드를 COM에 노출시키려면 속성 및 메서드를 클래스 인터페이스에 선언하고 `DispId` 특성으로 표시한 다음 클래스에 구현해야 합니다.  멤버는 인터페이스에 선언되는 순서에 따라 COM vtable에 사용됩니다.  
  
 클래스의 이벤트를 노출시키려면 이벤트 인터페이스에 이벤트를 선언하고 `DispId` 특성으로 표시해야 합니다.  클래스가 이 인터페이스를 구현해서는 안 됩니다.  
  
 클래스는 클래스 인터페이스를 구현합니다. 클래스는 여러 인터페이스를 구현할 수 있지만 구현된 첫 번째 인터페이스가 기본 클래스 인터페이스가 됩니다.  여기에서 COM에 노출되는 메서드 및 속성을 구현합니다.  이 메서드와 속성은 public으로 표시되어야 하며 클래스 인터페이스에 있는 선언과 일치해야 합니다.  여기에서는 클래스에 의해 발생되는 이벤트도 선언합니다.  이 메서드와 속성은 public으로 표시되어야 하며 이벤트 인터페이스에 있는 선언과 일치해야 합니다.  
  
## 예제  
 [!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [상호 운용성](../../../csharp/programming-guide/interop/interoperability.md)   
 [프로젝트 디자이너, 빌드 페이지\(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)