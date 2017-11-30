---
title: ".NET Framework의 내게 필요한 옵션의 새로운 기능"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="c20c1-102">.NET Framework의 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="c20c1-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="c20c1-103">.NET Framework 응용 프로그램 사용자에 대 한 자세한 accessibile 만드는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="c20c1-104">내게 필요한 옵션 기능 환경을 제공할 수 있도록 적절 한 사용자가 보조 기술에 대 한 응용 프로그램을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="c20c1-105">.NET Framework 4.7.1 부터는.NET Framework 액세스할 수 있는 응용 프로그램을 만드는 데 사용할 수 있는 내게 필요한 옵션 기능 향상의 다 수 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="c20c1-106">새로운 내게 필요한 옵션 기능은 4.7.1.NET Framework를 대상으로 하는 응용 프로그램에 대해 기본적으로 활성화 되어 이상이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="c20c1-107">또한 4.7.1.NET Framework에서 실행 되 고 또는 나중에 선택할 수 있지만 이전 버전의.NET Framework 대상 하는 응용 프로그램의 레거시 내게 필요한 옵션 동작 (및 함으로써.NET Framework 4.7.1의에서 내게 필요한 옵션 기능이 향상 옵트인) 하 여 다음 스위치를 추가 [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에는 [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) 응용 프로그램의 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="c20c1-108">4.7.1 부터는.NET Framework의 버전을 대상으로 하는 응용 프로그램에 다음 스위치를 추가 하 여 내게 필요한 옵션 기능을 비활성화할 수 마찬가지로,는 [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에는 [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) 응용 프로그램의 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="c20c1-109">.NET Framework 4.7.1의에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="c20c1-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="c20c1-110">.NET Framework 4.7.1에 다음과 같은 영역의 새 내게 필요한 옵션 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="c20c1-111">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="c20c1-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="c20c1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c20c1-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="c20c1-113">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="c20c1-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="c20c1-114">**화면 판독기 개선**</span><span class="sxs-lookup"><span data-stu-id="c20c1-114">**Screen reader improvements**</span></span>

<span data-ttu-id="c20c1-115">접근성 향상 된 기능을 사용할 경우.NET Framework 4.7.1 화면 판독기에 영향을 주는 다음과 같은 향상 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="c20c1-116">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.Expander> 단추가 화면 판독기가 발표 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="c20c1-117">.NET Framework 4.7.1 부터는 올바르게 별도로 공지 되 확장/축소 가능한 그룹 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="c20c1-118">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 화면 판독기가 "custom"으로 발표 된</span><span class="sxs-lookup"><span data-stu-id="c20c1-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="c20c1-119">.NET Framework 4.7.1 부터는 이제 올바르게 별도로 공지 되 데이터 표 형태 셀 (지역화 된)으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="c20c1-120">.NET Framework 4.7.1 부터는 화면 판독기의 편집 가능한 이름을 알리기 <xref:System.Windows.Controls.ComboBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="c20c1-121">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.PasswordBox> 컨트롤 "보기의 항목 없음"으로 발표 된 또는 잘못 된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="c20c1-122">이 문제는.NET Framework 4.7.1부터 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="c20c1-123">**UIAutomation LiveRegion 지원**</span><span class="sxs-lookup"><span data-stu-id="c20c1-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="c20c1-124">내레이터 도움말 사람과 같은 화면 판독기가 포커스가 있는 UI 콘텐츠의 텍스트 음성 변환 출력에 의해 응용 프로그램의 UI 내용을 읽고 하는 일반적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="c20c1-125">그러나 UI 요소를 변경 하 여 포커스가 없는 경우 사용자 알림이 표시 되지 않을 수 있습니다 및 중요 한 정보를 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="c20c1-126">이 문제를 해결할 수 있는 라이브 영역 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="c20c1-127">개발자는 화면 판독기 또는 다른 UIAutomation 클라이언트 UI 요소에 중요 한 변경 사항 이루어졌을 알리기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="c20c1-128">화면 판독기 방법 및 시점을 세울 수이 변경의 사용자에 게에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="c20c1-129">라이브 영역을 지원 하려면 다음과 같은 Api WPF에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="c20c1-130"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 식별 하는 필드는 **LiveSetting** 속성 및 **LiveRegionChanged** 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="c20c1-131">XAML을 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="c20c1-132">**AutomationProperties.LiveSetting** 연결 된 사용자에 대 한 UI 변경의 중요성 화면 판독기에 게 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="c20c1-133"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 을 식별 하는 **AutomationProperties.LiveSetting** 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="c20c1-134"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 제공 하는 재정의 될 수 있는 메서드는 **LiveSetting** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="c20c1-135"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 가져오고 설정 하는 메서드는 **LiveSetting** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="c20c1-136"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 다음과 같은 가능한을 정의 하는 열거형 **LiveSetting** 값:</span><span class="sxs-lookup"><span data-stu-id="c20c1-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="c20c1-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c20c1-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c20c1-138">요소는 라이브 영역의 콘텐츠 변경 된 경우 알림을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="c20c1-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c20c1-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c20c1-140">라이브 영역의 콘텐츠가 변경된 경우 요소는 비중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="c20c1-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c20c1-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c20c1-142">라이브 영역의 콘텐츠가 변경된 경우 요소는 중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="c20c1-143">LiveRegion 설정 하 여 만들 수 있습니다는 **AutomationProperties.LiveSetting** 다음 예제와 같이 관심 있는 요소의 속성에:</span><span class="sxs-lookup"><span data-stu-id="c20c1-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="c20c1-144">라이브 영역에 있는 데이터를 변경 하는 경우 화면 판독기에 알려야 할 하면 명시적으로 이벤트를 발생 다음 샘플과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="c20c1-145">**고대비**</span><span class="sxs-lookup"><span data-stu-id="c20c1-145">**High contrast**</span></span>

<span data-ttu-id="c20c1-146">.NET Framework 4.7.1 부터는 고대비의 향상 된 기능에 적용 된 다양 한 WPF 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="c20c1-147">이제 표시 되는 경우는 <xref:System.Windows.SystemParameters.HighContrast%2A> 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="c20c1-148">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-148">These include:</span></span>

- <span data-ttu-id="c20c1-149"><xref:System.Windows.Controls.Expander> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c20c1-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="c20c1-150">에 대 한 시각적 포커스는 <xref:System.Windows.Controls.Expander> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="c20c1-151">에 대 한 키보드 표시 <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, 및 <xref:System.Windows.Controls.RadioButton> 컨트롤이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="c20c1-152">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-152">For example:</span></span>

    <span data-ttu-id="c20c1-153">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-153">Before:</span></span> 
    
    ![내게 필요한 옵션 기능 향상 하기 전에 포커스가 있는 expander 컨트롤](media/expander-before.png)

    <span data-ttu-id="c20c1-155">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-155">After:</span></span> 

    ![내게 필요한 옵션 기능 향상 후 포커스가 있는 expander 컨트롤](media/expander-after.png)

- <span data-ttu-id="c20c1-157"><xref:System.Windows.Controls.CheckBox>및 <xref:System.Windows.Controls.RadioButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c20c1-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="c20c1-158">텍스트는 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤 보기에서 고대비 테마 선택 하면 쉽게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="c20c1-159">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-159">For example:</span></span>

    <span data-ttu-id="c20c1-160">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-160">Before:</span></span> 

    ![내게 필요한 옵션 기능 향상 하기 전에 포커스가 있는 고대비 라디오 단추](media/radio-button-before.png)
    
    <span data-ttu-id="c20c1-162">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-162">After:</span></span> 

    ![내게 필요한 옵션 기능 향상 후 포커스가 있는 고대비 라디오 단추](media/radio-button-after.png)

- <span data-ttu-id="c20c1-164"><xref:System.Windows.Controls.ComboBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c20c1-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="c20c1-165">.NET Framework 4.7.1, 비활성화 된 테두리부터 <xref:System.Windows.Controls.ComboBox> 컨트롤은 사용할 수 없는 텍스트 색입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="c20c1-166">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-166">For example:</span></span>
    
    <span data-ttu-id="c20c1-167">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-167">Before:</span></span> 

     ![콤보 상자 테두리와 텍스트 내게 필요한 옵션 기능 향상 하기 전에 사용 하지 않도록 설정](media/combo-disabled-before.png)

    <span data-ttu-id="c20c1-169">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-169">After:</span></span>   

     ![내게 필요한 옵션 기능 향상 이후에 테두리와 텍스트를 비활성화 하는 콤보 상자](media/combo-disabled-after.png)

    <span data-ttu-id="c20c1-171">또한 사용 안 함 및 포커스가 있는 단추는 올바른 테마 색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="c20c1-172">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-172">Before:</span></span>

    ![내게 필요한 옵션 기능 향상 하기 전에 단추 테마 색](media/button-themes-before.png) 
    
    <span data-ttu-id="c20c1-174">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-174">After:</span></span> 

    ![내게 필요한 옵션 기능 향상 후 단추 테마 색](media/button-themes-after.png) 

    <span data-ttu-id="c20c1-176">.NET Framework 4.7 및 이전 버전에서는 설정에서 마지막으로, 한 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일을 `Toolbar.ComboBoxStyleKey` 표시 되지 않도록 하려면 드롭다운 화살표를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="c20c1-177">이 문제는.NET Framework 4.7.1부터 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="c20c1-178">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-178">For example:</span></span>

    <span data-ttu-id="c20c1-179">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-179">Before:</span></span> 

    ![내게 필요한 옵션 기능 향상 하기 전에 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="c20c1-181">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-181">After:</span></span> 

    ![내게 필요한 옵션 기능 향상 후 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <span data-ttu-id="c20c1-183"><xref:System.Windows.Controls.DataGrid> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c20c1-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="c20c1-184">.NET Framework 4.7.1에 있는 정렬 표시기 화살표부터 <xref:System.Windows.Controls.DataGrid> 지금 사용 하 여 해결 테마 색을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="c20c1-185">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-185">For example:</span></span>

    <span data-ttu-id="c20c1-186">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-186">Before:</span></span> 

    ![내게 필요한 옵션 기능 향상 하기 전에 정렬 표시기 화살표](media/sort-indicator-before.png) 
    
    <span data-ttu-id="c20c1-188">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-188">After:</span></span>   
 
    ![내게 필요한 옵션 기능 향상 후 정렬 표시기 화살표](media/sort-indicator-after.png) 
    
    <span data-ttu-id="c20c1-190">또한.NET Framework 4.7 및 이전 버전에서는 기본 링크 스타일으로 변경 마우스에서 잘못 된 색을 통해 고대비 모드.</span><span class="sxs-lookup"><span data-stu-id="c20c1-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="c20c1-191">이.NET Framework 4.7.1부터 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="c20c1-192">마찬가지로, <xref:System.Windows.Controls.DataGrid> 확인란 열 예상 되는 색을 사용 하 여.NET Framework 4.7.1부터 키보드 포커스 피드백에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="c20c1-193">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-193">Before:</span></span> 

    ![내게 필요한 옵션 기능 향상 하기 전에 DataGrid 기본 링크 스타일](media/default-link-style-before.png) 
 
    <span data-ttu-id="c20c1-195">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-195">After:</span></span>    
  
    ![내게 필요한 옵션 기능 향상 후 DataGrid 기본 링크 스타일](media/default-link-style-after.png)  

<span data-ttu-id="c20c1-197">.NET Framework 4.7.1의에서 향상 된 WPF 내게 필요한 옵션 기능에 대 한 자세한 내용은 참조 하십시오. [WPF의 향상 된 접근성](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="c20c1-198">Windows Forms 내게 필요한 옵션 기능 향상</span><span class="sxs-lookup"><span data-stu-id="c20c1-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="c20c1-199">4.7.1.NET Framework Windows Forms (WinForms)에 다음 분야에서 내게 필요한 옵션 변경 내용을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="c20c1-200">**고대비 모드에서 향상 된 표시**</span><span class="sxs-lookup"><span data-stu-id="c20c1-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="c20c1-201">다양 한 WinForms 컨트롤.NET Framework 4.7.1 부터는 운영 체제에서 사용할 수 있는 고 대비 모드에서 향상 된 렌더링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="c20c1-202">Windows 10에 일부 고대비 시스템 색에 대 한 값을 변경 하 고 Windows 10 Win32 프레임 워크를 기반으로 하는 Windows Forms 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="c20c1-203">최상의 환경을 위해 최신 버전의 Windows에서 실행 한 다음 표시 되도록를 app.manifest 파일에는 테스트 응용 프로그램 및 Windows 10 주석 지원 OS 줄을 추가 하 여 최신 OS 변경에 옵트인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="c20c1-204">고대비 변경의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="c20c1-205">확인 표시 <xref:System.Windows.Forms.MenuStrip> 항목을 더 쉽게 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="c20c1-206">옵션을 선택 하면 비활성화 <xref:System.Windows.Forms.MenuStrip> 항목을 더 쉽게 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="c20c1-207">선택된 된 텍스트로 <xref:System.Windows.Forms.Button> 선택 색상으로 비교를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="c20c1-208">비활성된 텍스트 읽기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-208">Disabled text is easier to read.</span></span> <span data-ttu-id="c20c1-209">예:</span><span class="sxs-lookup"><span data-stu-id="c20c1-209">For example:</span></span>

    <span data-ttu-id="c20c1-210">이전:</span><span class="sxs-lookup"><span data-stu-id="c20c1-210">Before:</span></span>

    ![내게 필요한 옵션 기능 향상 하기 전에 비활성된 텍스트](media/wf-disabled-before.png) 

    <span data-ttu-id="c20c1-212">이후:</span><span class="sxs-lookup"><span data-stu-id="c20c1-212">After:</span></span>

    ![내게 필요한 옵션 기능 향상 후 사용할 수 없는 텍스트](media/wf-disabled-after.png) 

- <span data-ttu-id="c20c1-214">스레드 예외 대화 상자에서 고대비 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="c20c1-215">**내레이터 지원 향상된**</span><span class="sxs-lookup"><span data-stu-id="c20c1-215">**Improved Narrator support**</span></span>

<span data-ttu-id="c20c1-216">.NET framework 4.7.1 Windows Forms 내레이터에 대 한 다음과 같은 내게 필요한 옵션 개선 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="c20c1-217"><xref:System.Windows.Forms.MonthCalendar> 다른 UI 자동화 도구에 따라서도 내레이터, 컨트롤에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="c20c1-218"><xref:System.Windows.Forms.CheckedListBox> 컨트롤 목록 항목의 값을 변경 했습니다은 사용자가 알림을 있으므로 항목의 선택 상태가 변경 될 때 내레이터를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="c20c1-219"><xref:System.Windows.Forms.DataGridViewCell> 컨트롤 내레이터를 올바른 읽기 전용 상태를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="c20c1-220">내레이터 disabled 읽을 수 있습니다 <xref:System.Windows.Forms.ToolStripMenuItem> 텍스트, 이전에 비활성화 된 메뉴 항목 위에 건너 뛸 반면 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="c20c1-221">**UIAutomation 내게 필요한 옵션 패턴에 대 한 향상 된 지원**</span><span class="sxs-lookup"><span data-stu-id="c20c1-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="c20c1-222">내게 필요한 옵션 기술 도구 개발자는.NET Framework 4.7.1 부터는 API 내게 필요한 옵션의 일반 패턴 및 WinForms 컨트롤을 몇 개에 대 한 속성 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="c20c1-223">접근성 향상 된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="c20c1-224"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ToolStripSplitButton> 이제 지원는 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="c20c1-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> 이제 지원는 [toggle 패턴](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="c20c1-226"><xref:System.Windows.Forms.ToolStripItem> 지원는 <xref:System.Windows.Automation.AutomationElement.Name> 속성 및 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="c20c1-227"><xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 지원을 제어는 <xref:System.Windows.Automation.automationElement.Name> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="c20c1-228">**향상 된 속성 브라우저 경험**</span><span class="sxs-lookup"><span data-stu-id="c20c1-228">**Improved property browser experience**</span></span>

<span data-ttu-id="c20c1-229">.NET Framework 4.7.1 부터는 Windows Forms에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="c20c1-230">다양 한 드롭다운 선택 창을 통해 키보드 탐색 기능을 향상 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="c20c1-231">불필요 한 탭 정지의 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="c20c1-232">컨트롤 종류의 향상 된 보고 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-232">Better reporting of control types.</span></span>
- <span data-ttu-id="c20c1-233">향상 된 내레이터 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c20c1-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="c20c1-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c20c1-234">See Also</span></span>
[<span data-ttu-id="c20c1-235">.NET Framework의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="c20c1-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 