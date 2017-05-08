---
title: "연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 구성 요소, 도구 상자에 추가"
  - "IToolboxService 인터페이스"
  - "도구 상자[Windows Forms], 채우기"
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기
구성 요소는 현재 열려 있는 솔루션의 프로젝트에 정의되어 있는 경우 **도구 상자**에 자동으로 표시되므로 별도의 작업이 필요하지 않습니다.  [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)를 사용하여 **도구 상자**에 사용자 지정 구성 요소를 수동으로 채울 수도 있지만 **도구 상자**에서는 솔루션의 빌드 출력에 있는 항목이 다음 특성을 모두 갖는 것으로 간주합니다.  
  
-   <xref:System.ComponentModel.IComponent>를 구현합니다.  
  
-   <xref:System.ComponentModel.ToolboxItemAttribute>를 `false`로 설정하지 않습니다.  
  
-   <xref:System.ComponentModel.DesignTimeVisibleAttribute>를 `false`로 설정하지 않습니다.  
  
> [!NOTE]
>  **도구 상자**는 참조 체인을 따르지 않기 때문에 솔루션의 프로젝트에서 빌드되지 않는 항목을 표시하지 않습니다.  
  
 이 연습에서는 구성 요소가 빌드될 때 사용자 지정 구성 요소가 **도구 상자**에 자동으로 표시되는 방법을 보여 줍니다.  이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   사용자 지정 구성 요소 만들기  
  
-   사용자 지정 구성 요소 인스턴스 만들기  
  
-   사용자 지정 구성 요소 언로드 및 다시 로드  
  
 이 연습을 마치면 **도구 상자**에 사용자가 만든 구성 요소가 채워지게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  `ToolboxExample`이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  프로젝트에 새 구성 요소를 추가합니다.  구성 요소의 이름을 `DemoComponent`로 지정합니다.  
  
     자세한 내용은 [NIB:How to: Add New Project Items](http://msdn.microsoft.com/ko-kr/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)를 참조하십시오.  
  
3.  프로젝트를 빌드합니다.  
  
4.  **도구** 메뉴에서 **옵션** 항목을 클릭합니다.  **Windows Forms 디자이너** 항목 아래에서 **일반**을 클릭하고 **AutoToolboxPopulate** 옵션이 **True**로 설정되어 있는지 확인합니다.  
  
## 사용자 지정 구성 요소의 인스턴스 만들기  
 다음 단계는 폼에서 사용자 지정 구성 요소의 인스턴스를 만드는 것입니다.  **도구 상자**에서 새 구성 요소를 자동으로 고려하기 때문에 이 작업은 다른 구성 요소나 컨트롤을 만들 때처럼 쉽게 수행할 수 있습니다.  
  
#### 사용자 지정 구성 요소의 인스턴스를 만들려면  
  
1.  **폼 디자이너**에서 프로젝트의 폼을 엽니다.  
  
2.  **도구 상자**에서 **ToolboxExample 구성 요소**라는 새 탭을 클릭합니다.  
  
     해당 탭을 클릭하면 **DemoComponent**가 표시됩니다.  
  
    > [!NOTE]
    >  성능상의 이유로 **도구 상자**의 자동으로 채워진 영역에 있는 구성 요소는 사용자 지정 비트맵을 표시하지 않고 <xref:System.Drawing.ToolboxBitmapAttribute>가 지원되지 않습니다.  사용자 지정 구성 요소에 대한 아이콘을 **도구 상자**에 표시하려면 **도구 상자 항목 선택** 대화 상자를 사용하여 구성 요소를 업로드합니다.  
  
3.  구성 요소를 폼으로 끌어 옵니다.  
  
     구성 요소 인스턴스가 만들어지고 **구성 요소 트레이**에 추가됩니다.  
  
## 사용자 지정 구성 요소 언로드 및 다시 로드  
 **도구 상자**에서는 각 로드된 프로젝트의 구성 요소를 고려하므로, 프로젝트가 언로드되면 프로젝트의 구성 요소에 대한 참조가 제거됩니다.  
  
#### 구성 요소 언로드 및 다시 로드가 도구 상자에 미치는 영향을 확인하려면  
  
1.  프로젝트를 솔루션에서 언로드합니다.  
  
     프로젝트 언로드에 대한 자세한 내용은 [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/ko-kr/abc0155b-8fcb-4ffc-95b6-698518a7100b)를 참조하십시오.  저장할지를 묻는 메시지가 표시되면 **예**를 선택합니다.  
  
2.  솔루션에 새 **Windows 응용 프로그램** 프로젝트를 추가합니다.  **디자이너**에서 폼을 엽니다.  
  
     이전 프로젝트의 **ToolboxExample 구성 요소** 탭이 사라집니다.  
  
3.  `ToolboxExample` 프로젝트를 다시 로드합니다.  
  
     **ToolboxExample 구성 요소** 탭이 다시 나타납니다.  
  
## 다음 단계  
 이 연습에서는 **도구 상자**에서 프로젝트의 구성 요소를 고려하지만 컨트롤도 고려한다는 것을 보여 줍니다.  솔루션에서 컨트롤 프로젝트를 추가 및 제거하여 사용자 지정 컨트롤을 시험해 봅니다.  
  
## 참고 항목  
 [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/ko-kr/8dd170af-72f0-4212-b04b-034ceee92834)   
 [How to: Manipulate Toolbox Tabs](http://msdn.microsoft.com/ko-kr/21285050-cadd-455a-b1f5-a2289a89c4db)   
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)