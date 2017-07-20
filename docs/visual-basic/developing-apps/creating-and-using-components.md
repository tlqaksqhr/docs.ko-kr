---
title: "Visual Basic에서 구성 요소 만들기 및 사용 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 1235f62f6ac0878e16387c35150764f3585bc004
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="creating-and-using-components-in-visual-basic"></a>Visual Basic에서 구성 요소 만들기 및 사용
*구성 요소*는 <xref:System.ComponentModel.IComponent?displayProperty=fullName> 인터페이스를 구현하는 클래스이거나 <xref:System.ComponentModel.IComponent>를 구현하는 클래스에서 직접 또는 간접적으로 파생되는 클래스입니다. [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] 구성 요소는 재사용 가능한 개체이고, 다른 개체와 상호 작용할 수 있으며, 외부 리소스 및 디자인 타임 지원에 대한 제어를 제공합니다.  
  
 구성 요소의 중요한 기능은 구성 요소가 디자인 가능하다는 것입니다. 즉, 구성 요소인 클래스는 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] 통합 개발 환경에서 사용할 수 있습니다. 구성 요소는 도구 상자에 추가하고, 양식에 끌어서 놓고, 디자인 화면에서 조작할 수 있습니다. 구성 요소에 대한 기본 디자인 타임 지원은 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)]에 기본 제공됩니다. 구성 요소 개발자는 기본 디자인 타임 기능을 이용하기 위해 추가 작업을 할 필요가 없습니다.  
  
 *컨트롤*과 구성 요소는 둘 다 디자인 가능하다는 점에서 비슷합니다. 그러나 컨트롤은 사용자 인터페이스를 제공하지만 구성 요소는 제공하지 않습니다. 컨트롤은 기본 컨트롤 클래스인 <xref:System.Windows.Forms.Control> 또는 <xref:System.Web.UI.Control> 중 하나에서 파생되어야 합니다.  
  
## <a name="when-to-create-a-component"></a>구성 요소를 만들어야 하는 경우  
 클래스가 Design Surface(예: Windows Forms 또는 Web Forms 디자이너)에서 사용되지만 사용자 인터페이스가 없는 경우 클래스는 구성 요소로서, <xref:System.ComponentModel.IComponent>를 구현하거나 <xref:System.ComponentModel.IComponent>를 직접 또는 간접적으로 구현하는 클래스에서 파생되어야 합니다.  
  
 <xref:System.ComponentModel.Component> 및 <xref:System.ComponentModel.MarshalByValueComponent> 클래스는 <xref:System.ComponentModel.IComponent> 인터페이스의 기본 구현입니다. 이러한 클래스 간의 기본 차이점은 <xref:System.ComponentModel.Component> 클래스는 참조에 의해 마샬링되지만 <xref:System.ComponentModel.IComponent>는 값에 의해 마샬링된다는 점입니다. 다음 목록에서는 구현에 대한 다양한 지침을 제공합니다.  
  
-   구성 요소가 참조에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.Component>에서 파생합니다.  
  
-   구성 요소가 값에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.MarshalByValueComponent>에서 파생합니다.  
  
-   단일 상속으로 인해 구성 요소가 기본 구현 중 하나에서 파생될 수 없는 경우 <xref:System.ComponentModel.IComponent>를 구현합니다.  
  
 디자인 타임 지원에 대한 자세한 내용은 [구성 요소의 디자인 타임 특성](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) 및 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)을 참조하세요.  
  
## <a name="component-classes"></a>구성 요소 클래스  
 <xref:System.ComponentModel> 네임스페이스는 구성 요소와 컨트롤의 런타임 및 디자인 타임 동작을 구현하는 데 사용되는 클래스를 제공합니다. 이 네임스페이스에는 특성 및 형식 변환기를 구현하고, 데이터 소스에 바인딩하고, 구성 요소 사용을 허가하기 위한 기본 클래스 및 인터페이스가 포함됩니다.  
  
 핵심 구성 요소 클래스는 다음과 같습니다.  
  
-   <xref:System.ComponentModel.Component>. <xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다. 이 클래스를 통해 응용 프로그램 간에 개체를 공유할 수 있습니다.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>. <xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.  
  
-   <xref:System.ComponentModel.Container>. <xref:System.ComponentModel.IContainer> 인터페이스에 대한 기본 구현입니다. 이 클래스는 0 또는 추가 구성 요소를 캡슐화합니다.  
  
 구성 요소 라이선싱에 사용되는 일부 클래스는 다음과 같습니다.  
  
-   <xref:System.ComponentModel.License>. 모든 라이선스에 대한 추상 기본 클래스입니다. 라이선스는 구성 요소의 특정 인스턴스에 부여됩니다.  
  
-   <xref:System.ComponentModel.LicenseManager>. 라이선스를 구성 요소에 추가하고 <xref:System.ComponentModel.LicenseProvider>를 관리하기 위한 속성과 메서드를 제공합니다.  
  
-   <xref:System.ComponentModel.LicenseProvider>. 라이선스 공급자를 구현하기 위한 추상 기본 클래스입니다.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>. 클래스와 함께 사용할 <xref:System.ComponentModel.LicenseProvider> 클래스를 지정합니다.  
  
 구성 요소를 설명 및 유지하는 데 일반적으로 사용되는 클래스입니다.  
  
-   <xref:System.ComponentModel.TypeDescriptor>. 구성 요소의 특성, 속성 및 이벤트와 같이, 구성 요소의 특성에 대한 정보를 제공합니다.  
  
-   <xref:System.ComponentModel.EventDescriptor>. 이벤트에 대한 정보를 제공합니다.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>. 속성에 대한 정보를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [클래스, 구성 요소 및 컨트롤](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 *구성 요소* 및 *컨트롤*을 정의하고 이들 항목과 클래스 간의 차이점을 설명합니다.  
  
 [구성 요소 제작](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 구성 요소를 시작하기 위한 로드맵입니다.  
  
 [구성 요소 제작 연습](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 구성 요소 프로그래밍에 대한 단계별 지침을 제공하는 항목의 링크입니다.  
  
 [구성 요소 클래스](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 클래스를 구성 요소로 설정하는 작업, 구성 요소 기능을 표시하는 방법, 구성 요소에 대한 액세스 제어 및 구성 요소 인스턴스를 만드는 방법 제어를 설명합니다.  
  
 [컨트롤 및 구성 요소 제작 문제 해결](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 일반적인 문제 해결 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms에서 디자인 타임 지원 액세스](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)   
 [방법: 디자인 모드에서 컨트롤의 모양과 동작 확장](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b)   
 [방법: 디자인 모드에서 컨트롤에 대한 사용자 지정 초기화 수행](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)
