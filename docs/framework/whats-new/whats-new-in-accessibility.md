---
title: ".NET Framework에서 내게 필요한 옵션의 새로운 기능"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="6f702-102">.NET Framework에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6f702-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="6f702-103">.NET Framework는 응용 프로그램을 사용자에게 더욱 액세스 가능하도록 만드는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="6f702-104">내게 필요한 옵션 기능을 통해 응용 프로그램은 사용자에게 보조 기술에 대한 적절한 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="6f702-105">.NET Framework 4.7.1부터 .NET Framework에 개발자가 액세스 가능한 응용 프로그램을 만들도록 허용하는 다수의 내게 필요한 옵션 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="6f702-106">새로운 내게 필요한 옵션 기능은 .NET Framework 4.7.1 이상을 대상으로 하는 응용 프로그램에 대해 기본적으로 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="6f702-107">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 응용 프로그램은 응용 프로그램의 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가하여 레거시 내게 필요한 옵션 동작을 옵트아웃할 수 있습니다(따라서 .NET Framework 4.7.1에서 내게 필요한 옵션 개선 사항으로 옵트인).</span><span class="sxs-lookup"><span data-stu-id="6f702-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="6f702-108">마찬가지로 4.7.1부터 시작하는 .NET Framework의 버전을 대상으로 하는 응용 프로그램은 응용 프로그램의 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가하여 내게 필요한 옵션 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="6f702-109">.NET Framework 4.7.1에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6f702-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="6f702-110">.NET Framework 4.7.1에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="6f702-111">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="6f702-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="6f702-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f702-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="6f702-113">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="6f702-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="6f702-114">**화면 판독기 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="6f702-114">**Screen reader improvements**</span></span>

<span data-ttu-id="6f702-115">내게 필요한 옵션 개선 사항이 활성화된 경우 .NET Framework 4.7.1에는 화면 판독기에 영향을 주는 다음과 같은 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="6f702-116">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.Expander> 컨트롤은 단추로 화면 판독기에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="6f702-117">.NET Framework 4.7.1부터 확장/축소 가능한 그룹으로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="6f702-118">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 “사용자 지정”으로 화면 판독기에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="6f702-119">.NET Framework 4.7.1부터 이제 데이터 표 셸(지역화된)로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="6f702-120">.NET Framework 4.7.1부터 화면 판독기는 편집 가능한 <xref:System.Windows.Controls.ComboBox>의 이름을 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="6f702-121">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.PasswordBox> 컨트롤은 "보기에 항목 없음"으로 공지되었거나 그렇지 않은 경우 잘못된 동작이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="6f702-122">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="6f702-123">**UIAutomation LiveRegion 지원**</span><span class="sxs-lookup"><span data-stu-id="6f702-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="6f702-124">내레이터와 같은 화면 판독기는 사용자가 일반적으로 포커스가 있는 UI 콘텐츠의 텍스트 음성 변환 출력에 의해 응용 프로그램의 UI 콘텐츠를 읽는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="6f702-125">그러나 UI 요소가 변경되고 포커스가 없는 경우 사용자는 알림을 받지 못하고 중요한 정보를 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="6f702-126">라이브 영역은 이 문제를 해결하는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="6f702-127">개발자는 화면 판독기 또는 다른 UIAutomation 클라이언트에게 UI 요소에 중요한 변경 내용이 만들어졌음을 알리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="6f702-128">화면 판독기는 사용자에게 이 변경 내용을 알리는 방법 및 시점을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="6f702-129">라이브 영역을 지원하기 위해 다음과 같은 API가 WPF에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="6f702-130">**LiveSetting** 속성 및 **LiveRegionChanged** 이벤트를 식별하는 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 필드</span><span class="sxs-lookup"><span data-stu-id="6f702-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="6f702-131">XAML을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="6f702-132">화면 판독기에 사용자에 대한 UI 변경 내용의 중요성을 알리는 **AutomationProperties.LiveSetting** 연결된 속성</span><span class="sxs-lookup"><span data-stu-id="6f702-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="6f702-133">**AutomationProperties.LiveSetting** 연결된 속성을 식별하는 <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="6f702-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="6f702-134">**LiveSetting** 값을 제공하도록 재정의될 수 있는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="6f702-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="6f702-135">**LiveSetting** 값을 가져오고 설정하는 <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="6f702-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="6f702-136">다음 가능한 **LiveSetting** 값을 정의하는 <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 열거형</span><span class="sxs-lookup"><span data-stu-id="6f702-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="6f702-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f702-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f702-138">라이브 영역의 콘텐츠가 변경된 경우 요소는 알림을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="6f702-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f702-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f702-140">라이브 영역의 콘텐츠가 변경된 경우 요소는 비중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="6f702-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f702-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f702-142">라이브 영역의 콘텐츠가 변경된 경우 요소는 중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="6f702-143">다음 예제와 같이 관심 있는 요소에 **AutomationProperties.LiveSetting** 속성을 설정하여 LiveRegion을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="6f702-144">라이브 영역에 있는 데이터가 변경되고 화면 판독기에 알려야 하는 경우 다음 샘플과 같이 명시적으로 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="6f702-145">**고대비**</span><span class="sxs-lookup"><span data-stu-id="6f702-145">**High contrast**</span></span>

<span data-ttu-id="6f702-146">.NET Framework 4.7.1부터 다양한 WPF 컨트롤에 고대비의 개선 사항이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="6f702-147"><xref:System.Windows.SystemParameters.HighContrast%2A> 테마가 설정된 경우 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="6f702-148">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-148">These include:</span></span>

- <span data-ttu-id="6f702-149"><xref:System.Windows.Controls.Expander> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6f702-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="6f702-150"><xref:System.Windows.Controls.Expander> 컨트롤에 대한 포커스 시각적 개체는 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="6f702-151"><xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤에 대한 키보드 시각적 개체도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="6f702-152">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-152">For example:</span></span>

    <span data-ttu-id="6f702-153">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-153">Before:</span></span> 
    
    ![내게 필요한 옵션 개선 사항 이전의 포커스가 있는 Expander 컨트롤](media/expander-before.png)

    <span data-ttu-id="6f702-155">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-155">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 포커스가 있는 Expander 컨트롤](media/expander-after.png)

- <span data-ttu-id="6f702-157"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6f702-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="6f702-158"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤의 텍스트는 이제 고대비 테마에서 선택하면 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="6f702-159">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-159">For example:</span></span>

    <span data-ttu-id="6f702-160">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-160">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 포커스가 있는 고대비 라디오 단추](media/radio-button-before.png)
    
    <span data-ttu-id="6f702-162">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-162">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 포커스가 있는 고대비 라디오 단추](media/radio-button-after.png)

- <span data-ttu-id="6f702-164"><xref:System.Windows.Controls.ComboBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6f702-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="6f702-165">.NET Framework 4.7.1부터 비활성화된 <xref:System.Windows.Controls.ComboBox> 컨트롤의 테두리는 비활성화된 텍스트와 동일한 색입니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="6f702-166">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-166">For example:</span></span>
    
    <span data-ttu-id="6f702-167">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-167">Before:</span></span> 

     ![내게 필요한 옵션 개선 사항 이전의 콤보 상자 비활성화된 테두리 및 텍스트](media/combo-disabled-before.png)

    <span data-ttu-id="6f702-169">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-169">After:</span></span>   

     ![내게 필요한 옵션 개선 사항 이후의 콤보 상자 비활성화된 테두리 및 텍스트](media/combo-disabled-after.png)

    <span data-ttu-id="6f702-171">또한 비활성화되고 포커스가 있는 단추는 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="6f702-172">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-172">Before:</span></span>

    ![내게 필요한 옵션 개선 사항 이전의 단추 테마 색](media/button-themes-before.png) 
    
    <span data-ttu-id="6f702-174">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-174">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 단추 테마 색](media/button-themes-after.png) 

    <span data-ttu-id="6f702-176">마지막으로 .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일을 `Toolbar.ComboBoxStyleKey`로 설정하면 드롭다운 화살표가 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="6f702-177">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="6f702-178">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-178">For example:</span></span>

    <span data-ttu-id="6f702-179">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-179">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="6f702-181">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-181">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <span data-ttu-id="6f702-183"><xref:System.Windows.Controls.DataGrid> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6f702-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="6f702-184">.NET Framework 4.7.1부터 <xref:System.Windows.Controls.DataGrid> 컨트롤의 정렬 표시기 화살표는 이제 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="6f702-185">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-185">For example:</span></span>

    <span data-ttu-id="6f702-186">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-186">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 정렬 표시기 화살표](media/sort-indicator-before.png) 
    
    <span data-ttu-id="6f702-188">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-188">After:</span></span>   
 
    ![내게 필요한 옵션 개선 사항 이후의 정렬 표시기 화살표](media/sort-indicator-after.png) 
    
    <span data-ttu-id="6f702-190">또한 .NET Framework 4.7 이전 버전에서 기본 링크 스타일은 고대비 모드의 마우스에서 잘못된 색으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="6f702-191">이는 .NET Framework 4.7.1부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="6f702-192">마찬가지로 <xref:System.Windows.Controls.DataGrid> 확인란 열은 .NET Framework 4.7.1부터 키보드 포커스 피드백에 대해 예상되는 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="6f702-193">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-193">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 DataGrid 기본 링크 스타일](media/default-link-style-before.png) 
 
    <span data-ttu-id="6f702-195">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-195">After:</span></span>    
  
    ![내게 필요한 옵션 개선 사항 이후의 DataGrid 기본 링크 스타일](media/default-link-style-after.png)  

<span data-ttu-id="6f702-197">.NET Framework 4.7.1에서 WPF 내게 필요한 옵션 개선 사항에 대한 자세한 내용은 [WPF의 내게 필요한 옵션 개선 사항](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f702-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="6f702-198">Windows Forms 내게 필요한 옵션 개선 사항</span><span class="sxs-lookup"><span data-stu-id="6f702-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="6f702-199">.NET Framework 4.7.1에서 WinForms(Windows Forms)는 다음 영역에서 내게 필요한 옵션 변경 내용을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="6f702-200">**고대비 모드에서 향상된 표시**</span><span class="sxs-lookup"><span data-stu-id="6f702-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="6f702-201">.NET Framework 4.7.1부터 다양한 WinForms 컨트롤은 운영 체제에서 사용할 수 있는 고대비 모드의 향상된 렌더링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="6f702-202">Windows 10은 일부 고대비 시스템 색에 대한 값을 변경했으며 Windows Forms는 Windows 10 Win32 프레임워크를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="6f702-203">최상의 환경을 위해 최신 버전의 Windows를 실행하고 테스트 응용 프로그램에 app.manifest 파일을 추가하여 최신 OS로 옵트인하고 다음과 같이 보이도록 Windows 10 지원되는 OS 줄에 대한 주석을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="6f702-204">고대비 변경 내용의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="6f702-205"><xref:System.Windows.Forms.MenuStrip> 항목의 확인 표시는 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="6f702-206">선택하면 비활성화된 <xref:System.Windows.Forms.MenuStrip> 항목이 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="6f702-207">선택된 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 선택 영역 색과 대비됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="6f702-208">비활성화된 텍스트는 읽기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-208">Disabled text is easier to read.</span></span> <span data-ttu-id="6f702-209">예:</span><span class="sxs-lookup"><span data-stu-id="6f702-209">For example:</span></span>

    <span data-ttu-id="6f702-210">이전:</span><span class="sxs-lookup"><span data-stu-id="6f702-210">Before:</span></span>

    ![내게 필요한 옵션 개선 사항 이전의 비활성화된 텍스트](media/wf-disabled-before.png) 

    <span data-ttu-id="6f702-212">이후:</span><span class="sxs-lookup"><span data-stu-id="6f702-212">After:</span></span>

    ![내게 필요한 옵션 개선 사항 이후의 비활성화된 텍스트](media/wf-disabled-after.png) 

- <span data-ttu-id="6f702-214">스레드 예외 대화 상자의 고대비 개선 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="6f702-215">**향상된 내레이터 지원**</span><span class="sxs-lookup"><span data-stu-id="6f702-215">**Improved Narrator support**</span></span>

<span data-ttu-id="6f702-216">.NET Framework 4.7.1에서 Windows Forms는 내레이터에 대한 다음과 같은 내게 필요한 옵션 개선 사항을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="6f702-217"><xref:System.Windows.Forms.MonthCalendar> 컨트롤은 내레이터 및 다른 UI 자동화 도구로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="6f702-218"><xref:System.Windows.Forms.CheckedListBox> 컨트롤은 항목의 선택 상태가 변경되어 목록 항목의 값을 변경했음을 사용자에게 알릴 때 내레이터에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="6f702-219"><xref:System.Windows.Forms.DataGridViewCell> 컨트롤은 올바른 읽기 전용 상태를 내레이터에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="6f702-220">내레이터는 이제 비활성화된 <xref:System.Windows.Forms.ToolStripMenuItem> 텍스트를 읽을 수 있는 반면 이전에는 비활성화된 메뉴 항목을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="6f702-221">**UIAutomation 내게 필요한 옵션 패턴에 대한 향상된 지원**</span><span class="sxs-lookup"><span data-stu-id="6f702-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="6f702-222">.NET Framework 4.7.1부터 내게 필요한 옵션 기술 도구의 개발자는 API 내게 필요한 옵션의 일반 패턴 및 여러 WinForms 컨트롤에 대한 속성을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="6f702-223">이러한 내게 필요한 옵션 개선 사항은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="6f702-224"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ToolStripSplitButton>은 이제 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="6f702-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell>은 이제 [토글 패턴](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="6f702-226"><xref:System.Windows.Forms.ToolStripItem> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성 및 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="6f702-227"><xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="6f702-228">**향상된 속성 브라우저 환경**</span><span class="sxs-lookup"><span data-stu-id="6f702-228">**Improved property browser experience**</span></span>

<span data-ttu-id="6f702-229">.NET Framework 4.7.1부터 Windows Forms는 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6f702-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="6f702-230">다양한 드롭다운 선택 창을 통한 향상된 키보드 탐색</span><span class="sxs-lookup"><span data-stu-id="6f702-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="6f702-231">불필요한 탭 정지의 감소</span><span class="sxs-lookup"><span data-stu-id="6f702-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="6f702-232">컨트롤 형식의 향상된 보고</span><span class="sxs-lookup"><span data-stu-id="6f702-232">Better reporting of control types.</span></span>
- <span data-ttu-id="6f702-233">향상된 내레이터 동작</span><span class="sxs-lookup"><span data-stu-id="6f702-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="6f702-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f702-234">See Also</span></span>
[<span data-ttu-id="6f702-235">.NET Framework의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6f702-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 