---
title: "Creating and Using Components in Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "components [Visual Basic]"
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Creating and Using Components in Visual Basic
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

*구성 요소*는 <xref:System.ComponentModel.IComponent?displayProperty=fullName> 인터페이스를 구현하거나 <xref:System.ComponentModel.IComponent>를 구현하는 클래스에서 직접 또는 간접적으로 파생되는 클래스입니다.  [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] 구성 요소는 재사용이 가능하고, 다른 개체와 상호 작용할 수 있으며, 외부 리소스에 대한 제어 및 디자인 타임 지원을 제공하는 개체입니다.  
  
 구성 요소의 중요한 기능은 디자인이 가능하다는 점입니다. 즉, 구성 요소인 클래스를 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)] 통합 개발 환경에서 사용할 수 있습니다.  구성 요소는 도구 상자에 추가할 수 있고, 폼에 끌어다 놓을 수 있으며, 디자인 화면에서 조작할 수 있습니다.  구성 요소에 대한 기본 디자인 타임 지원은 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]에 기본으로 적용된 기능이므로 구성 요소 개발자는 기본 디자인 타임 기능을 이용하기 위해 추가 작업을 수행할 필요가 없습니다.  
  
 *컨트롤*은 디자인이 가능하다는 점에서 구성 요소와 비슷합니다.  하지만 구성 요소와 달리 컨트롤은 사용자 인터페이스를 제공합니다.  컨트롤은 기본 컨트롤 클래스인 <xref:System.Windows.Forms.Control> 또는 <xref:System.Web.UI.Control> 중 하나에서 파생되어야 합니다.  
  
## 구성 요소를 만들어야 하는 경우  
 Windows Forms 또는 Web Forms 디자이너와 같은 디자인 화면에서 클래스를 사용하려고 하는데 이 클래스에 사용자 인터페이스가 없다면 이 클래스는 구성 요소이면서 <xref:System.ComponentModel.IComponent>를 구현하거나, <xref:System.ComponentModel.IComponent>를 직접 또는 간접적으로 구현하는 클래스에서 파생되어야 합니다.  
  
 <xref:System.ComponentModel.Component> 및 <xref:System.ComponentModel.MarshalByValueComponent> 클래스는 <xref:System.ComponentModel.IComponent> 인터페이스의 기본 구현입니다.  이들 클래스 간의 주된 차이점은 <xref:System.ComponentModel.Component> 클래스는 참조로 마샬링되는 반면 <xref:System.ComponentModel.IComponent>는 값으로 마샬링된다는 점입니다.  다음은 구현하기 위한 전반적인 지침입니다.  
  
-   구성 요소를 참조로 마샬링해야 하는 경우에는 <xref:System.ComponentModel.Component>에서 파생시킵니다.  
  
-   구성 요소를 값으로 마샬링해야 하는 경우에는 <xref:System.ComponentModel.MarshalByValueComponent>에서 파생시킵니다.  
  
-   단일 상속으로 인해 구성 요소를 기본 구현 중 하나에서 파생시킬 수 없는 경우에는 <xref:System.ComponentModel.IComponent>를 구현합니다.  
  
 디자인 타임 지원에 대한 자세한 내용은 [구성 요소의 디자인 타임 특성](../Topic/Design-Time%20Attributes%20for%20Components.md) 및 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)을 참조하십시오.  
  
## 구성 요소 클래스  
 <xref:System.ComponentModel> 네임스페이스는 구성 요소와 컨트롤의 런타임 및 디자인 타임 동작을 구현하는 데 사용되는 클래스를 제공합니다.  이 네임스페이스는 특성 및 형식 변환기의 구현, 데이터 소스에 바인딩, 구성 요소 라이센스 등에 필요한 기본 클래스와 인터페이스를 포함합니다.  
  
 핵심 구성 요소 클래스는 다음과 같습니다.  
  
-   <xref:System.ComponentModel.Component>.  <xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.  이 클래스를 통해 응용 프로그램 간의 개체 마샬링이 가능합니다.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>.  <xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.  
  
-   <xref:System.ComponentModel.Container>.  <xref:System.ComponentModel.IContainer> 인터페이스에 대한 기본 구현입니다.  이 클래스는 0개 이상의 구성 요소를 캡슐화합니다.  
  
 구성 요소 라이센스에 사용되는 일부 클래스는 다음과 같습니다.  
  
-   <xref:System.ComponentModel.License>.  모든 라이선스에 대한 추상 기본 클래스입니다.  라이센스는 구성 요소의 특정 인스턴스에 부여됩니다.  
  
-   <xref:System.ComponentModel.LicenseManager>.  구성 요소에 라이선스를 추가하고 <xref:System.ComponentModel.LicenseProvider>를 관리하는 속성 및 메서드를 제공합니다.  
  
-   <xref:System.ComponentModel.LicenseProvider>.  라이선스 공급자를 구현하기 위한 추상 기본 클래스입니다.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>.  클래스에 사용할 <xref:System.ComponentModel.LicenseProvider> 클래스를 지정합니다.  
  
 일반적으로 구성 요소의 설명과 유지에 사용되는 클래스입니다.  
  
-   <xref:System.ComponentModel.TypeDescriptor>.  특성, 속성 및 이벤트와 같은 구성 요소의 특징에 대한 정보를 제공합니다.  
  
-   <xref:System.ComponentModel.EventDescriptor>.  이벤트에 대한 정보를 제공합니다.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>.  속성에 대한 정보를 제공합니다.  
  
## 관련 단원  
 [클래스, 구성 요소 및 컨트롤](../Topic/Class%20vs.%20Component%20vs.%20Control.md)  
 *구성 요소*와 *컨트롤*을 정의하고 이들과 클래스 간의 차이를 설명합니다.  
  
 [구성 요소 제작](../Topic/Component%20Authoring.md)  
 구성 요소의 사용을 시작하기 위한 로드맵입니다.  
  
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)  
 구성 요소 프로그래밍을 위한 단계별 지침을 제공하는 항목들을 안내합니다.  
  
 [구성 요소 클래스](../Topic/Component%20Classes.md)  
 클래스를 구성 요소로 만드는 요소, 구성 요소 기능을 노출하는 방법, 구성 요소에 대한 액세스 제어 및 구성 요소 인스턴스가 만들어지는 방법 제어에 대해 설명합니다.  
  
 [컨트롤 및 구성 요소 제작 문제 해결](../Topic/Troubleshooting%20Control%20and%20Component%20Authoring.md)  
 일반적인 문제를 해결하는 방법에 대해 설명합니다.  
  
## 참고 항목  
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)   
 [How to: Extend the Appearance and Behavior of Controls in Design Mode](../Topic/How%20to:%20Extend%20the%20Appearance%20and%20Behavior%20of%20Controls%20in%20Design%20Mode.md)   
 [How to: Perform Custom Initialization for Controls in Design Mode](../Topic/How%20to:%20Perform%20Custom%20Initialization%20for%20Controls%20in%20Design%20Mode.md)