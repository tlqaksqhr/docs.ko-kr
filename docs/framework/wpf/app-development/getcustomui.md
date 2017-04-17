---
title: "GetCustomUI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 오류 메시지[WPF]"
  - "GetCustomUI 메서드"
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# GetCustomUI
구현되는 경우 호스트에서 사용자 지정 진행률과 오류 메시지를 가져오기 위해 PresentationHost.exe에 의해 호출됩니다.  
  
## 구문  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### 매개 변수  
 `pwzProgressAssemblyName`  
  
 \[out\] 호스트 제공 진행률 사용자 인터페이스가 포함된 어셈블리에 대한 포인터입니다.  
  
 `pwzProgressClassName`  
  
 \[out\] 호스트 제공 진행률 사용자 인터페이스인 클래스의 이름입니다. 가능한 <xref:System.Windows.Controls.Page>가 있는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일이 해당 클래스의 최상위 요소여야 합니다.  이 클래스는 `pwzProgressAssemblyName`에 의해 지정되는 어셈블리에 있습니다.  
  
 `pwzErrorAssemblyName`  
  
 \[out\] 호스트 제공 오류 사용자 인터페이스가 포함된 어셈블리에 대한 포인터입니다.  
  
 `pwzErrorClassName`  
  
 \[out\] 호스트 제공 오류 사용자 인터페이스인 클래스의 이름입니다. 가능한 <xref:System.Windows.Controls.Page>가 있는 XAML 파일이 해당 클래스의 최상위 요소여야 합니다.  이 클래스는 `pwzErrorAssemblyName`에 의해 지정되는 어셈블리에 있습니다.  
  
## 속성 값\/반환 값  
 HRESULT: 무시되었습니다.  
  
## 설명  
 호스트 응용 프로그램에는 PresentationHost.exe의 기본 사용자 인터페이스가 따르지 않을 수 있는 특정 테마가 있습니다.  이 경우 호스트 응용 프로그램은 [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)를 구현하여 진행률 및 오류 사용자 인터페이스를 PresentationHost.exe에 반환할 수 있습니다.  PresentationHost.exe는 기본 사용자 인터페이스를 사용하기 전에 항상 [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)를 호출합니다.  
  
 이 함수는 PresentationHost의 초기화 중에 한 번만 호출됩니다.  
  
## 참고 항목  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)