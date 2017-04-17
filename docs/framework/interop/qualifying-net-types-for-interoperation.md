---
title: "상호 운용할 .NET 형식의 정규화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, COM 구성 요소 게시"
  - "COM interop, .NET 형식 정규화"
  - ".NET Framework 구성 요소를 COM에 노출"
  - "비관리 코드와의 상호 운용, .NET Framework 구성 요소 게시"
  - "비관리 코드와의 상호 운용, .NET 형식 정규화"
  - "상호 운용할 .NET 형식의 정규화"
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 상호 운용할 .NET 형식의 정규화
어셈블리의 형식을 COM 응용 프로그램에 노출시키려면 디자인 타임의 COM interop 요구 사항을 고려해야 합니다.  다음 지침을 따르면 관리되는 형식\(클래스, 인터페이스, 구조체 및 열거형\)과 COM 형식이 매끄럽게 통합되도록 할 수 있습니다.  
  
-   클래스에서 인터페이스를 명시적으로 구현해야 합니다.  
  
     COM interop에서는 클래스의 모든 멤버와 기본 클래스의 모든 멤버를 포함하는 인터페이스를 자동으로 생성하는 메커니즘을 제공하지만 이 기능보다는 명시적 인터페이스를 사용하는 것이 좋습니다.  자동으로 생성되는 인터페이스를 클래스 인터페이스라고 합니다.  여기에 대한 지침은 [클래스 인터페이스 소개](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)를 참조하십시오.  
  
     [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# 및 C\+\+를 사용하면 IDL\(Interface Definition Language\) 또는 이에 해당하는 기능을 사용하지 않고도 코드에 인터페이스 정의를 통합할 수 있습니다.  구문에 대한 자세한 내용은 해당 언어의 설명서를 참조하십시오.  
  
-   관리되는 형식은 공용이어야 합니다.  
  
     어셈블리의 공용 형식만 등록되어 형식 라이브러리에 내보내지기 때문에  COM에서는 공용 형식만 볼 수 있습니다.  
  
     관리되는 형식은COM에는 노출되지 않는 기능을 다른 관리 코드에 노출하는데,  예를 들어 매개 변수가 있는 생성자, 정적 메서드 및 상수 필드는 COM 클라이언트에는 표시되지 않습니다.  또한 런타임에서 형식의 데이터를 마샬링할 때 데이터가 복사되거나 변환될 수 있습니다.  
  
-   메서드, 속성, 필드 및 이벤트는 공용이어야 합니다.  
  
     공용 형식의 멤버 역시 공용이어야 COM에 표시됩니다.  <xref:System.Runtime.InteropServices.ComVisibleAttribute>를 적용하면 어셈블리, 공용 형식 또는 공용 형식의 공용 멤버 표시 여부를 제한할 수 있습니다.  기본적으로 모든 공용 형식 및 멤버가 표시됩니다.  
  
-   형식에는 COM에서 활성화될 공용 기본 생성자가 있어야 합니다.  
  
     관리되는 공용 형식은 COM에 표시되지만  공용 기본 생성자\(인수가 없는 생성자\)가 없으면 COM 클라이언트에서는 형식을 만들 수 없습니다.  COM 클라이언트는 다른 방법으로 활성화되는 경우에도 형식을 사용할 수 있어야 합니다.  
  
-   형식은 추상이어서는 안 됩니다.  
  
     COM 클라이언트와 .NET 클라이언트는 추상 형식을 만들 수 없습니다.  
  
 관리되는 형식의 상속 계층 구조는 COM에 내보내질 때 결합됩니다.  버전 관리도 관리되는 환경과 관리되지 않는 환경에 따라 다르며  COM에 노출된 형식의 버전 관리 특성은 다른 관리되는 형식의 버전 관리 특성과 다릅니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Interop 특성 적용](../../../docs/framework/interop/applying-interop-attributes.md)   
 [COM에서 사용할 어셈블리의 패키징](../../../docs/framework/interop/packaging-an-assembly-for-com.md)