---
title: "x:Code Intrinsic XAML Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Code"
  - "x:Code"
  - "xCode"
helpviewer_keywords: 
  - "Code directive in XAML [XAML Services]"
  - "x:Code XAML directive element [XAML Services]"
  - "XAML [XAML Services], x:Code directive element"
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: 19
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 19
---
# x:Code Intrinsic XAML Type
XAML 프로덕션 내에 코드를 배치할 수 있습니다.  이런 코드는 XAML을 컴파일하는 XAML 프로세서 구현에 의해 컴파일되거나 런타임에 해석 같이 나중에 사용하기 위해 XAML 프로덕션에 남겨질 수 있습니다.  
  
## XAML 개체 요소 사용  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## 설명  
 `x:Code` XAML 지시문 요소 내의 코드는 여전히 제공된 일반 XML 네임스페이스와 XAML 내에서 해석됩니다.  따라서 `CDATA` 세그먼트 안에서 사용되는 코드를 `x:Code`로 묶어야 합니다.  
  
 `x:Code`가 XAML 프로덕션 파일의 가능한 모든 배포 메커니즘에 대해 허용되는 것은 아닙니다.  특정 프레임워크\(예: WPF\)에서는 코드를 컴파일해야 합니다.  다른 프레임워크에서 `x:Code` 사용은 일반적으로 허용되지 않을 수 있습니다.  
  
 관리되는 `x:Code` 콘텐츠를 허용하는 프레임워크의 경우 `x:Code` 콘텐츠에 대해 사용할 언어 컴파일러는 응용 프로그램 컴파일에 사용되는 포함 프로젝트의 설정 및 대상에 따라 결정됩니다.  
  
## WPF 사용 정보  
 WPF에 대해 `x:Code` 안에서 선언되는 코드에는 몇 가지 중요한 제한이 있습니다.  
  
-   `x:Code` 지시문 요소는 XAML 프로덕션 루트 요소의 바로 아래 자식 요소여야 합니다.  
  
-   [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)는 부모 루트 요소에 제공되어야 합니다.  
  
-   `x:Code` 안에 있는 코드는 컴파일할 때 해당 XAML 페이지에 대해 이미 생성된 partial 클래스의 범위 내에 있는 것으로 취급됩니다.  따라서 정의하는 모든 코드가 해당 partial 클래스의 멤버 또는 변수여야 합니다.  
  
-   partial 클래스 안에 클래스를 중첩하는 방법\(중첩된 클래스는 XAML에서 참조할 수 없으므로 잘못된 방법은 아니지만 일반적이지는 않음\) 이외에는 추가 클래스를 정의할 수 없습니다.  기존 partial 클래스에 대해 사용되는 네임스페이스 이외의 다른 CLR 네임스페이스는 정의하거나 추가할 수 없습니다.  
  
-   partial 클래스 CLR 네임스페이스 외부의 코드 엔터티에 대한 참조는 모두 정규화되어야 합니다.  선언 중인 멤버가 partial 클래스 재정의 가능한 멤버로 재정의되는 경우에는 언어별 재정의 키워드로 이를 지정해야 합니다.  멤버가 컴파일러가 충돌을 보고하는 방식으로 XAML에서 생성된 partial 클래스의 멤버와 `x:Code` 범위에서 충돌을 선언한 경우에는 XAML 파일을 로드하거나 컴파일할 수 없습니다.  
  
## 참고 항목  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [WPF의 코드 숨김 및 XAML](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [XAML 개요\(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)