---
title: "방법: 응용 프로그램 설정 유효성 검사 | Microsoft Docs"
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
  - "응용 프로그램 설정, 유효성 검사"
  - "응용 프로그램 설정, Windows Forms"
  - "응용 프로그램 설정 유효성 검사"
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 응용 프로그램 설정 유효성 검사
이 항목에서는 응용 프로그램 설정을 유지하기 전에 유효성을 검사하는 방법을 보여 줍니다.  
  
 응용 프로그램 설정은 강력한 형식이므로 사용자는 지정된 설정에 잘못된 형식의 데이터를 할당할 수 없습니다.  그러나 사용자가 허용되는 범위 밖의 값을 설정에 할당하려고 시도할 수 있습니다. 예를 들면, 생일을 오늘 이후 날짜로 입력할 수 있습니다.  모든 응용 프로그램 설정 클래스의 부모 클래스인 <xref:System.Configuration.ApplicationSettingsBase>는 이러한 범위를 검사할 수 있는 네 가지 이벤트를 노출합니다.  이 세 가지 이벤트를 처리하면 모든 유효성 검사 코드가 프로젝트 전체에 분산되지 않고 한 곳에 배치됩니다.  
  
 다음 표에 설명된 대로 설정의 유효성을 검사해야 하는 시점에 따라 사용할 이벤트가 달라집니다.  
  
|Event|발생 및 용도|  
|-----------|-------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|설정 속성 그룹을 처음 로드한 후에 발생합니다.<br /><br /> 전체 속성 그룹의 초기 값을 응용 프로그램 내에서 사용하기 전에 유효성을 검사하려면 이 이벤트를 사용합니다.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|단일 설정 속성 값을 변경하기 전에 발생합니다.<br /><br /> 단일 속성을 변경하기 전에 유효성을 검사하려면 이 이벤트를 사용합니다.  이 이벤트는 해당 작업 및 선택 항목에 대한 즉각적인 피드백을 사용자에게 제공할 수 있습니다.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|단일 설정 속성 값을 변경한 후에 발생합니다.<br /><br /> 단일 속성을 변경한 후에 유효성을 검사하려면 이 이벤트를 사용합니다.  시간이 오래 걸리는 비동기 유효성 검사 프로세스가 필요한 경우가 아니면 이 이벤트는 유효성 검사에 거의 사용되지 않습니다.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|설정 속성 그룹을 저장하기 전에 발생합니다.<br /><br /> 전체 속성 그룹의 값을 디스크에 유지하기 전에 유효성을 검사하려면 이 이벤트를 사용합니다.|  
  
 일반적으로 동일한 응용 프로그램 내에서 유효성 검사를 위해 이러한 이벤트를 모두 사용하지는 않습니다.  예를 들어, <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 이벤트만 처리해도 모든 유효성 검사 요구 사항이 충족되는 경우가 많습니다.  
  
 일반적으로 이벤트 처리기는 잘못된 값을 발견할 경우 다음 작업 중 하나를 수행합니다.  
  
-   기본값과 같은 올바른 값을 자동으로 적용합니다.  
  
-   정보에 대한 서버 코드의 사용자를 다시 쿼리합니다.  
  
-   <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 및 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>과 같이 관련된 작업보다 먼저 발생하는 이벤트에서는 <xref:System.ComponentModel.CancelEventArgs> 인수를 사용하여 작업을 취소합니다.  
  
 이벤트 처리에 대한 자세한 내용은 [이벤트 처리기 개요](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)를 참조하십시오.  
  
 다음 프로시저에서는 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 또는 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> 이벤트를 사용하여 생일이 올바른지 테스트하는 방법을 보여 줍니다.  응용 프로그램 설정은 이미 만들어져 있는 것으로 전제하고 작성한 프로시저입니다. 이 예제에서는 `DateOfBirth`라는 설정에 대한 범위를 검사합니다.  설정 만들기에 대한 자세한 내용은 [방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)를 참조하십시오.  
  
### 응용 프로그램 설정 개체를 가져오려면  
  
-   다음 글머리 기호 항목 중 하나를 수행하여 응용 프로그램 설정 개체\(래퍼 인스턴스\)에 대한 참조를 가져옵니다.  
  
    -   **속성 편집기**에서 Visual Studio 응용 프로그램 설정 대화 상자를 사용하여 설정을 만들었으면 다음 식을 통해 해당 언어에 대해 생성된 기본 설정 개체를 검색할 수 있습니다.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         또는  
  
    -   Visual Basic 개발자가 프로젝트 디자이너를 사용하여 응용 프로그램 설정을 만들었으면 [My.Settings 개체](../../../../ocs/visual-basic/language-reference/objects/my-settings-object.md)를 사용하여 설정을 검색할 수 있습니다.  
  
         또는  
  
    -   <xref:System.Configuration.ApplicationSettingsBase>에서 직접 파생시켜 설정을 만들었으면 클래스를 수동으로 인스턴스화해야 합니다.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 다음 프로시저는 이 프로시저의 마지막 글머리 기호 항목을 수행하여 응용 프로그램 설정을 가져온 것으로 가정한 상태에서 작성되었습니다.  
  
### 설정을 변경할 때 응용 프로그램 설정의 유효성을 검사하려면  
  
1.  C\# 개발자는 폼이나 컨트롤의 `Load` 이벤트에 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
     또는  
  
     Visual Basic 개발자는 `WithEvents` 키워드를 사용하여 `Settings` 변수를 선언해야 합니다.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  이벤트 처리기를 정의하고 이 처리기 내부에 코드를 작성하여 생일의 범위를 검사합니다.  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### 저장이 발생할 때 응용 프로그램 설정의 유효성을 검사하려면  
  
1.  폼이나 컨트롤의 `Load` 이벤트에 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  이벤트 처리기를 정의하고 이 처리기 내부에 코드를 작성하여 생일의 범위를 검사합니다.  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## 참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)