---
title: "사용자 지정 컨트롤에 대한 응용 프로그램 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f8292ac459a2943376229ef62466b0a772430dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="application-settings-for-custom-controls"></a>사용자 지정 컨트롤에 대한 응용 프로그램 설정
사용자 지정 컨트롤 컨트롤 공급 업체 응용 프로그램에서 호스팅되는 응용 프로그램 설정을 유지 하는 기능을 제공 하려면 특정 작업을 완료 해야 합니다.  
  
 대부분의 응용 프로그램 설정 기능에 대 한 설명서는 독립 실행형 응용 프로그램을 만들고 있다는 가정 아래에 기록 됩니다. 그러나 응용 프로그램에서 다른 개발자가 호스트 하는 컨트롤을 만드는 경우 해야 해당 설정을 유지 하기 위해 컨트롤에 대 한 몇 가지 추가 단계가 제대로 합니다.  
  
## <a name="application-settings-and-custom-controls"></a>응용 프로그램 설정 및 사용자 지정 컨트롤  
 제대로 해당 설정을 유지 하기 위해 컨트롤에 대 한 프로세스 자체 전용된 응용 프로그램 설정 래퍼 클래스에서 파생 된 만들어 캡슐화 해야 것 <xref:System.Configuration.ApplicationSettingsBase>합니다. 또한 주 제어 클래스 구현 해야 합니다는 <xref:System.Configuration.IPersistComponentSettings>합니다. 인터페이스에는 두 가지 방법 뿐 아니라 여러 속성이 포함 되어 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 및 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>합니다. 사용 하 여 폼에 컨트롤을 추가 하는 경우는 **Windows Forms 디자이너** Visual Studio에서는 Windows Forms 호출 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 컨트롤을 초기화할 경우에 자동으로 호출 해야 합니다. <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 에서 직접는 `Dispose` 컨트롤의 메서드를 제공 합니다.  
  
 또한 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동 하려면 사용자 지정 컨트롤에 대 한 응용 프로그램 설정에 대 한 순서에는 다음을 구현 해야 합니다.  
  
1.  생성자를 사용 하는 사용자 지정 응용 프로그램 설정 클래스는 <xref:System.ComponentModel.IComponent> 단일 매개 변수로 합니다. 이 클래스를 사용 하 여 저장 하 고 모든 응용 프로그램 설정을 로드 합니다. 이 클래스의 새 인스턴스를 만들 때 생성자를 사용 하 여 사용자 지정 컨트롤을 전달 합니다.  
  
2.  컨트롤 생성 되 고과 같은 폼의 폼에 배치 된 후이 사용자 지정 설정 클래스를 만들 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.  
  
 사용자 지정 설정 클래스를 만드는 방법에 지침은 [하는 방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)합니다.  
  
## <a name="settings-keys-and-shared-settings"></a>설정 키 및 공유 설정  
 일부 컨트롤은 동일한 폼 내에서 여러 번 사용할 수 있습니다. 대부분의 경우 이러한 컨트롤을 개별 설정을 유지 합니다. 와 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 속성 <xref:System.Configuration.IPersistComponentSettings>, 여러 버전의 폼에 컨트롤을 명확 하 게 되는 고유 문자열을 제공할 수 있습니다.  
  
 구현 하는 가장 간단한 방법은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 사용 하는 것은 <xref:System.Windows.Forms.Control.Name%2A> 에 대 한 컨트롤의 속성은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>합니다. 값을 전달 로드 하거나 컨트롤의 설정을 저장할 때 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 에 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 의 속성은 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다. 사용자의 설정을 XML 유지 하는 경우이 고유 키를 사용 하는 응용 프로그램 설정 합니다. 다음 코드 예제와 어떻게는 `<userSettings>` 섹션 이라는 사용자 지정 컨트롤의 인스턴스를 찾는 `CustomControl1` 에 대 한 설정을 저장 하는 `Text` 속성.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 에 대 한 값을 제공 하지 않는 컨트롤의 모든 인스턴스가 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 동일한 설정을 공유 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [응용 프로그램 설정 아키텍처](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
