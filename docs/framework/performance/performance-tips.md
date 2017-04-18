---
title: ".NET 성능 팁 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "C# 언어, 성능"
  - "성능[C#]"
  - "성능[Visual Basic]"
  - "Visual Basic, 성능"
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
caps.handback.revision: 36
---
# .NET 성능 팁
*성능*이라는 용어는 일반적으로 프로그램의 실행 속도를 의미합니다.  경우에 따라 소스 코드의 특정 기본 규칙에 따라 실행 속도를 높일 수 있습니다.  코드를 자세히 검사한 후 프로파일러를 사용하여 최대한 빠른 속도로 실행해야 하는 프로그램도 있으며,  코드가 작성된 대로 적합한 속도로 실행되므로 최적화를 수행하지 않아도 되는 프로그램도 있습니다.  이 문서에는 성능이 저하될 수 있는 몇 가지 일반 영역 및 이를 개선할 수 있는 팁 및 추가 성능 항목에 대한 링크가 나와 있습니다.  성능을 계획하고 측정하는 방법에 대한 자세한 내용은 [Performance](../../../docs/framework/performance/index.md)을 참조하십시오.  
  
## boxing 및 unboxing  
 <xref:System.Collections.ArrayList?displayProperty=fullName> 같은 제네릭이 아닌 컬렉션 클래스의 예와 같이 많은 수의 boxing이 필요한 경우에는 값 형식을 사용하지 않는 것이 좋습니다.  <xref:System.Collections.Generic.List%601?displayProperty=fullName> 같은 제네릭 컬렉션을 사용하면 값 형식의 boxing을 방지할 수 있습니다.  boxing 및 unboxing 과정에는 많은 처리 작업이 필요합니다.  값 형식을 boxing할 때는 완전히 새로운 개체가 만들어져야 하며,  이러한 작업은 간단한 참조 할당보다 최대 20배의 시간이 걸립니다.  unboxing을 할 때는 캐스팅 과정에 할당 작업보다 4배의 시간이 걸릴 수 있습니다.  자세한 내용은 [Boxing 및 Unboxing](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md)을 참조하십시오.  
  
## 문자열  
 예를 들어, 자주 반복되는 루프에서 많은 수의 문자열 변수를 연결하는 경우 C\# [\+ operator](../Topic/+%20Operator%20\(C%23%20Reference\).md) 또는 Visual Basic [연결 연산자](../Topic/Concatenation%20Operators%20\(Visual%20Basic\).md) 대신 <xref:System.Text.StringBuilder?displayProperty=fullName>를 사용합니다.  자세한 내용은 [방법: 여러 문자열 연결](../Topic/How%20to:%20Concatenate%20Multiple%20Strings%20\(C%23%20Programming%20Guide\).md) 및 [Concatenation Operators in Visual Basic](../Topic/Concatenation%20Operators%20in%20Visual%20Basic.md)를 참조하십시오.  
  
## 소멸자  
 빈 소멸자는 사용하지 않는 것이 좋습니다.  클래스에 소멸자가 있으면 종료 큐에 항목이 만들어집니다.  소멸자가 호출되면 큐 처리를 위해 가비지 수집기가 호출됩니다.  그러므로 빈 소멸자는 성능 저하를 가져올 뿐입니다.  자세한 내용은 [소멸자](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md) 및 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)를 참조하십시오.  
  
## 기타 리소스  
  
-   [보다 빠른 관리 코드 작성: 비용 확인](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [고성능 관리 응용 프로그램 작성: 기본](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [가비지 수집기 기본 및 성능 힌트](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [성능 팁 및 .NET 응용 프로그램 사용법](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [.NET용 내부 진단 도구](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Rico Mariani의 성능 정보](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## 참고 항목  
 [Performance](../../../docs/framework/performance/index.md)   
 [프로그래밍 개념](../Topic/Programming%20Concepts.md)   
 [Visual Basic Programming Guide](../Topic/Visual%20Basic%20Programming%20Guide.md)   
 [C\# 프로그래밍 가이드](../Topic/C%23%20Programming%20Guide.md)