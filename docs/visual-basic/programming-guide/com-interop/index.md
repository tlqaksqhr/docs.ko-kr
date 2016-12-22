---
title: "COM Interop (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "Visual Basic code, COM interop"
  - "COM interop, in Visual Basic"
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# COM Interop (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

COM\(Component Object Model\)은 개체의 기능을 다른 구성 요소 및 호스트 응용 프로그램에 노출할 수 있도록 합니다.  오늘날 대부분의 소프트웨어에는 COM 개체가 포함되어 있습니다.  새 응용 프로그램에 .NET 어셈블리를 사용하는 것이 가장 좋기는 하지만 간혹 COM 개체를 사용해야 할 경우도 있습니다.  이 단원에서는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 COM 개체를 작성하고 사용하는 데 관련된 몇 가지 문제를 설명합니다.  
  
## 단원 내용  
 [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 COM 상호 운용성에 대해 간략하게 설명합니다.  
  
 [How to: Reference COM Objects from Visual Basic](../Topic/How%20to:%20Reference%20COM%20Objects%20from%20Visual%20Basic.md)  
 형식 라이브러리가 있는 COM 개체에 대한 참조를 추가하는 방법을 설명합니다.  
  
 [How to: Work with ActiveX Controls](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 기존의 ActiveX 컨트롤을 사용하여 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 도구 상자에 기능을 추가하는 방법을 보여 줍니다.  
  
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 Windows 운영 체제의 일부인 API를 호출하는 과정을 단계별로 수행합니다.  
  
 [How to: Call Windows APIs](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 User32.dll에서 `MessageBox` 함수를 정의하고 호출하는 방법을 보여 줍니다.  
  
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 부호 없는 형식에는 매개 변수가 Windows 함수를 호출 하는 방법을 보여 줍니다.  
  
 [Walkthrough: Creating COM Objects with Visual Basic](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 COM 클래스 템플릿을 사용하거나 사용하지 않고 COM 개체를 만드는 과정을 단계별로 안내합니다.  
  
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 COM을 사용할 때 발생할 수 있는 몇 가지 문제점을 설명합니다.  
  
 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 COM 개체와 .NET Framework 개체를 같은 응용 프로그램에서 사용하는 방법에 대한 개요를 설명합니다.  
  
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 기존의 COM 개체를 새 개체의 기본으로 사용하는 방법을 설명합니다.  
  
## 관련 단원  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)  
 공용 언어 런타임에서 제공하는 상호 운용성 서비스에 대해 설명합니다.  
  
 [.NET Framework에 COM 구성 요소 노출](../Topic/Exposing%20COM%20Components%20to%20the%20.NET%20Framework.md)  
 COM interop를 통하여 COM 형식을 호출하는 프로세스에 대해 설명합니다.  
  
 [.NET Framework 구성 요소를 COM에 노출](../Topic/Exposing%20.NET%20Framework%20Components%20to%20COM.md)  
 COM의 관리되는 형식을 준비 및 사용하는 방법에 대해 설명합니다.  
  
 [Interop 특성 적용](../Topic/Applying%20Interop%20Attributes.md)  
 비관리 코드로 작업할 때 사용할 수 있는 특성에 대해 설명합니다.