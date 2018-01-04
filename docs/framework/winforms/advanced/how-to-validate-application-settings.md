---
title: "방법: 응용 프로그램 설정 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e12620a5079efaba4faa9101253a3a586965b7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="c3ff5-102">방법: 응용 프로그램 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c3ff5-102">How to: Validate Application Settings</span></span>
<span data-ttu-id="c3ff5-103">이 항목에서는 응용 프로그램 설정이 유지되기 전에 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>  
  
 <span data-ttu-id="c3ff5-104">응용 프로그램 설정이 강력한 형식이기 때문에 사용자가 지정된 설정에 잘못된 형식의 데이터를 할당할 수 없다는 점이 어느 정도 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="c3ff5-105">그러나 사용자가 설정에 허용 가능한 범위 밖의 값을 할당하려고 시도할 수 있습니다(예: 미래의 생년월일 제공).</span><span class="sxs-lookup"><span data-stu-id="c3ff5-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="c3ff5-106"><xref:System.Configuration.ApplicationSettingsBase>이러한 범위를 검사할 수 있도록 4 개의 이벤트를 노출 하는 모든 응용 프로그램 설정 클래스의 부모 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="c3ff5-107">이러한 이벤트를 처리하면 모든 유효성 검사 코드를 프로젝트 전체에 분산하지 않고 단일 위치에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>  
  
 <span data-ttu-id="c3ff5-108">다음 표에 설명된 대로 사용할 이벤트는 설정의 유효성을 검사해야 하는 경우에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>  
  
|<span data-ttu-id="c3ff5-109">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="c3ff5-109">Event</span></span>|<span data-ttu-id="c3ff5-110">발생 및 사용</span><span class="sxs-lookup"><span data-stu-id="c3ff5-110">Occurrence and use</span></span>|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="c3ff5-111">설정 속성 그룹을 초기 로드한 이후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="c3ff5-112">이 이벤트를 사용하여 전체 속성 그룹 초기 값을 응용 프로그램 내에서 사용하기 전에 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="c3ff5-113">단일 설정 속성의 값이 변경되기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="c3ff5-114">이 이벤트를 사용하여 단일 속성을 변경하기 전에 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="c3ff5-115">해당 작업 및 선택 항목에 관한 즉각적인 피드백을 사용자에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="c3ff5-116">단일 설정 속성의 값이 변경된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="c3ff5-117">이 이벤트를 사용하여 단일 속성을 변경한 후에 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="c3ff5-118">이 이벤트는 시간이 오래 걸리는 비동기 유효성 검사 프로세스가 필요한 경우가 아니면 거의 유효성 검사에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="c3ff5-119">설정 속성 그룹이 저장되기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="c3ff5-120">이 이벤트를 사용하여 전체 속성 그룹 값을 디스크에 유지하기 전에 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|  
  
 <span data-ttu-id="c3ff5-121">일반적으로 유효성을 검사하기 위해 동일한 응용 프로그램 내에서 이러한 모든 이벤트를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="c3ff5-122">예를 들어 된 수만 처리 하 여 모든 유효성 검사 요구 사항을 충족 하는 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
 <span data-ttu-id="c3ff5-123">이벤트 처리기가 잘못된 값을 감지하면 일반적으로 다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>  
  
-   <span data-ttu-id="c3ff5-124">기본 값과 같이 올바른 것으로 알려진 값을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-124">Automatically supplies a value known to be correct, such as the default value.</span></span>  
  
-   <span data-ttu-id="c3ff5-125">정보에 대한 서버 코드의 사용자를 다시 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-125">Re-queries the user of server code for information.</span></span>  
  
-   <span data-ttu-id="c3ff5-126">와 같은 관련된 작업, 하기 전에 발생 한 이벤트에 대 한 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 및 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>를 사용 하 여는 <xref:System.ComponentModel.CancelEventArgs> 작업을 취소 하는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>  
  
 <span data-ttu-id="c3ff5-127">이벤트를 처리하는 방법에 대한 자세한 내용은 [이벤트 처리기 개요](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-127">For more information about event handling, see [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="c3ff5-128">다음 절차 중 하나를 사용 하 여 올바른 생년월일에 대 한 테스트 하는 방법을 보여는 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 또는 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="c3ff5-129">프로시저는 응용 프로그램 설정을 이미 만들었다는 가정 하에서 작성되었습니다. 이 예제에서는 `DateOfBirth`라는 설정에 대한 범위 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="c3ff5-130">설정을 만드는 방법에 대한 자세한 내용은 [방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-130">For more information about creating settings, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="c3ff5-131">응용 프로그램 설정 개체를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="c3ff5-131">To obtain the application settings object</span></span>  
  
-   <span data-ttu-id="c3ff5-132">다음 글머리 기호 항목 중 하나를 완료하여 응용 프로그램 설정 개체(래퍼 인스턴스)에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>  
  
    -   <span data-ttu-id="c3ff5-133">**속성 편집기**에서 Visual Studio 응용 프로그램 설정 대화 상자를 사용하여 설정을 만든 경우 다음 식을 통해 언어에 대해 생성된 기본 설정 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         <span data-ttu-id="c3ff5-134">또는</span><span class="sxs-lookup"><span data-stu-id="c3ff5-134">-or-</span></span>  
  
    -   <span data-ttu-id="c3ff5-135">사용자가 Visual Basic 개발자이며 프로젝트 디자이너를 사용하여 응용 프로그램 설정을 만든 경우 [My.Settings 개체](~/docs/visual-basic/language-reference/objects/my-settings-object.md)를 사용하여 설정을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
         <span data-ttu-id="c3ff5-136">또는</span><span class="sxs-lookup"><span data-stu-id="c3ff5-136">-or-</span></span>  
  
    -   <span data-ttu-id="c3ff5-137">파생 하 여 설정을 만든 경우 <xref:System.Configuration.ApplicationSettingsBase> 를 직접 클래스를 수동으로 인스턴스화해야 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 <span data-ttu-id="c3ff5-138">다음 절차는 이 절차에서 마지막 글머리 기호 항목을 완료하여 응용 프로그램 설정 개체를 가져왔다는 가정 하에서 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="c3ff5-139">설정이 변경될 때 응용 프로그램 설정 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="c3ff5-139">To validate Application Settings when a setting is changing</span></span>  
  
1.  <span data-ttu-id="c3ff5-140">폼 이나 컨트롤의 C# 개발자를 모르는 경우 `Load` 이벤트를 이벤트 처리기에 대 한 추가 <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
     <span data-ttu-id="c3ff5-141">또는</span><span class="sxs-lookup"><span data-stu-id="c3ff5-141">-or-</span></span>  
  
     <span data-ttu-id="c3ff5-142">사용자가 Visual Basic 개발자인 경우 `WithEvents` 키워드를 사용하여 `Settings` 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>  
  
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
  
2.  <span data-ttu-id="c3ff5-143">이벤트 처리기를 정의하고 내부에 코드를 작성하여 생년월일에 대한 범위 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="c3ff5-144">저장이 발생할 때 응용 프로그램 설정의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="c3ff5-144">To validate Application Settings when a Save occurs</span></span>  
  
1.  <span data-ttu-id="c3ff5-145">폼 이나 컨트롤의 `Load` 이벤트를 이벤트 처리기에 대 한 추가 <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>  
  
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
  
2.  <span data-ttu-id="c3ff5-146">이벤트 처리기를 정의하고 내부에 코드를 작성하여 생년월일에 대한 범위 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ff5-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c3ff5-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3ff5-147">See Also</span></span>  
 [<span data-ttu-id="c3ff5-148">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="c3ff5-148">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="c3ff5-149">방법: 응용 프로그램 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="c3ff5-149">How to: Create Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
