---
title: "x:Members Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# x:Members Directive
부모 요소의 x:Class에 적용되는 태그에 정의된 구성원 집합을 보유합니다.  
  
## XAML 특성 사용  
  
```  
  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`className`|XAML 프로덕션을 위한 지원 클래스 또는 partial 클래스의 이름입니다.  설명 부분을 참조하십시오.|  
|`oneOrMoreMembers`|멤버 정의를 나타내는 하나 이상의 개체 요소입니다.  일반적으로 이러한 요소는 `x:Property` 개체 요소입니다.  설명 부분을 참조하십시오.|  
  
## 설명  
 .NET Framework XAML 서비스 구현에서 `x:Members`에 대한 지원 클래스 또는 기본 멤버 구현이 없습니다.  `x:Members`는 모든 형식에서 구성원으로 존재할 수 있는 특수 XAML 구성원입니다.  XAML 노드 스트림에서 `x:Members`는 XAML 언어 XAML 네임스페이스에서 `Members`라는 멤버로 표현됩니다.  멤버 `Members`에는 `Member` 개체의 읽기 전용 제네릭 목록이 포함되어 있습니다.  일반적인 태그에서 개별 구성원은 `x:Property` 속성 요소로 지정됩니다.  `x:Property`는 형식의 속성을 위해 특별히 더 정밀한 형식이며 `x:Member`에 할당할 수 있습니다.  자세한 내용은 [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md)를 참조하십시오.  
  
 태그에서 멤버 정의를 지정하기 위한 수단으로 `x:Members`의 실질적인 사용을 지원하기 위해 멤버는 수정 가능한 클래스와 연결되어 있어야 합니다.  의도한 모델은 `x:Members`를 지정하는 형식의 멤버로 존재하는 `x:Class`입니다.  그러나 형식과 멤버를 연결하고 동적 멤버 정의를 생성하는 메커니즘은 .NET Framework XAML 서비스 수준에서 지원되지 않습니다.  이것은 XAML의 멤버 정의를 지원하는 응용 프로그램 모델을 가진 개별 프레임워크 왼쪽에 있습니다.  일반적으로 이 기능을 지원하는 데 XAML을 태그 컴파일하고 코드 숨김 기능과 통합되거나 XAML 어셈블리에서 순수 생산하는 MSBUILD 빌드 작업이 필요합니다.  
  
## Windows Workflow Foundation의 x:Members  
 Windows Workflow Foundation의 경우 `x:Members`에는 전적으로 XAML에서 구성된 사용자 정의 활동의 구성원 또는 코드 숨김을 사용하여 활동 디자이너에 대한 XAML 정의 동적 구성원이 포함되어 있습니다.  `x:Class`는 XAML 프로덕션의 루트 요소에만 지정해야 합니다.  이는 .NET Framework XAML 서비스 수준의 요구 사항이 아니지만 XAML 프로덕션이 일반적으로 사용자 지정 활동 및 Windows Workflow Foundation XAML을 지원하는 MSBUILD 빌드 작업을 통해 로드되는 경우에는 요구 사항이 됩니다.  `x:Members`는 `x:Class`을 선언하는 개체 요소의 태그에서 첫 번째 자식 요소여야 합니다.