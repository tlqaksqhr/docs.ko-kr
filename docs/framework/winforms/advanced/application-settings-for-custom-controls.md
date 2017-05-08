---
title: "사용자 지정 컨트롤에 대한 응용 프로그램 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "응용 프로그램 설정[Windows Forms], 사용자 지정 컨트롤"
  - "사용자 지정 컨트롤[Windows Forms], 응용 프로그램 설정"
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 사용자 지정 컨트롤에 대한 응용 프로그램 설정
타사 응용 프로그램에서 컨트롤을 호스팅할 때 응용 프로그램 설정을 유지할 수 있는 기능을 사용자 지정 컨트롤에 제공하려면 특정 작업을 수행해야 합니다.  
  
 응용 프로그램 설정 기능에 대한 대부분의 설명서는 독립 실행형 응용 프로그램을 만드는 경우를 전제로 하여 작성되었습니다.  그러나 다른 개발자가 자신의 응용 프로그램에서 호스팅할 컨트롤을 만드는 경우 설정을 제대로 유지하기 위해서는 컨트롤에 대한 몇 가지 추가 단계를 수행해야 합니다.  
  
## 응용 프로그램 설정 및 사용자 지정 컨트롤  
 컨트롤에서 설정을 제대로 유지하려면 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되는 전용 응용 프로그램 설정 래퍼 클래스를 만들어 프로세스를 캡슐화해야 합니다.  또한 기본 컨트롤 클래스에서 <xref:System.Configuration.IPersistComponentSettings>를 구현해야 합니다.  여러 속성과 함께 두 가지 메서드, 즉 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 및 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>가 인터페이스에 포함되어 있습니다.  Visual Studio에서 **Windows Forms 디자이너**를 사용하여 폼에 컨트롤을 추가하면 컨트롤이 초기화될 때 Windows Forms에서 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>가 자동으로 호출됩니다. <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>는 컨트롤의 `Dispose` 메서드에서 직접 호출해야 합니다.  
  
 또한 사용자 지정 컨트롤의 응용 프로그램 설정이 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동하도록 하려면 다음을 구현해야 합니다.  
  
1.  <xref:System.ComponentModel.IComponent>를 단일 매개 변수로 사용하는 생성자가 포함된 사용자 지정 응용 프로그램 설정 클래스를 구현합니다.  이 클래스를 사용하여 모든 응용 프로그램 설정을 저장하고 로드합니다.  이 클래스의 새 인스턴스를 만들 때는 생성자를 사용하여 사용자 지정 컨트롤을 전달합니다.  
  
2.  폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서와 같이 폼에 컨트롤을 만들어 배치한 후 이 사용자 지정 설정 클래스를 만듭니다.  
  
 사용자 지정 설정 클래스를 만드는 방법에 대한 자세한 내용은 [방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)를 참조하십시오.  
  
## 설정 키 및 공유 설정  
 같은 폼 내에서 여러 번 사용할 수 있는 컨트롤도 일부 있습니다.  대부분의 경우 이러한 컨트롤에서는 개별 설정을 유지해야 합니다.  <xref:System.Configuration.IPersistComponentSettings>에서 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 속성을 사용하여 폼에서 여러 버전의 컨트롤을 구분해 주는 고유 문자열을 입력할 수 있습니다.  
  
 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>를 가장 간단하게 구현하려면 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>에 대해 컨트롤의 <xref:System.Windows.Forms.Control.Name%2A> 속성을 사용합니다.  컨트롤의 설정을 로드하거나 저장할 때 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>의 값을 <xref:System.Configuration.ApplicationSettingsBase> 클래스의 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 속성에 전달합니다.  응용 프로그램 설정에서는 사용자의 설정을 XML로 유지할 때 이 고유 키를 사용합니다.  다음 코드 예제에서는 `<userSettings>` 섹션에서 `Text` 속성에 대한 설정을 저장하는 `CustomControl1`이라는 사용자 지정 컨트롤의 인스턴스를 찾는 방법을 보여 줍니다.  
  
```  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>의 값을 제공하지 않는 컨트롤의 모든 인스턴스는 동일한 설정을 공유합니다.  
  
## 참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.IPersistComponentSettings>   
 [응용 프로그램 설정 아키텍처](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)