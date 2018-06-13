---
title: .NET Framework에서 내게 필요한 옵션의 새로운 기능
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fe7e15e482028b9988d7e560b98be19b6c07427
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509218"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="cd094-102">.NET Framework에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="cd094-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="cd094-103">.NET Framework는 응용 프로그램을 사용자에게 더욱 액세스 가능하도록 만드는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="cd094-104">내게 필요한 옵션 기능을 통해 응용 프로그램은 사용자에게 보조 기술에 대한 적절한 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="cd094-105">.NET Framework 4.7.1부터 .NET Framework에 개발자가 액세스 가능한 응용 프로그램을 만들도록 허용하는 다수의 내게 필요한 옵션 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

## <a name="accessibility-switches"></a><span data-ttu-id="cd094-106">내게 필요한 옵션 스위치</span><span class="sxs-lookup"><span data-stu-id="cd094-106">Accessibility switches</span></span>

<span data-ttu-id="cd094-107">.NET Framework 4.7 이전 버전을 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 경우 내게 필요한 옵션 기능으로 옵트인하도록 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="cd094-108">.NET Framework 4.7.1 이상을 대상으로 하는 경우 레거시 기능(및 내게 필요한 옵션 기능을 활용하지 못하도록)을 사용하도록 앱을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="cd094-109">내게 필요한 옵션 기능을 포함하는 .NET Framework의 각 버전에는 응용 프로그램의 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 추가하는 버전별 내게 필요한 옵션 스위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="cd094-110">다음은 지원되는 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-110">The following are the supported switches:</span></span>

|<span data-ttu-id="cd094-111">버전</span><span class="sxs-lookup"><span data-stu-id="cd094-111">Version</span></span>|<span data-ttu-id="cd094-112">전환</span><span class="sxs-lookup"><span data-stu-id="cd094-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="cd094-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="cd094-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="cd094-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="cd094-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="cd094-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="cd094-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="cd094-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="cd094-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="cd094-117">내게 필요한 옵션 개선 사항 활용</span><span class="sxs-lookup"><span data-stu-id="cd094-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="cd094-118">새로운 내게 필요한 옵션 기능은 .NET Framework 4.7.1 이상을 대상으로 하는 응용 프로그램에 대해 기본적으로 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="cd094-119">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 응용 프로그램은 응용 프로그램의 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 스위치를 추가하고 해당 값을 `false`로 설정하여 레거시 내게 필요한 옵션 동작을 옵트아웃할 수 있습니다(따라서 내게 필요한 옵션 개선 사항 활용).</span><span class="sxs-lookup"><span data-stu-id="cd094-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="cd094-120">다음은 .NET Framework 4.7.1에 도입된 내게 필요한 옵션 개선 사항으로 옵트인하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="cd094-121">.NET Framework의 이후 버전에서 내게 필요한 옵션 기능으로 옵트인하도록 선택한 경우 .NET Framework의 이전 버전에서도 기능으로 명시적으로 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="cd094-122">.NET Framework 4.7.1 및 4.7.2 모두에서 내게 필요한 옵션 개선 사항을 활용하도록 앱을 구성하려면 다음 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="cd094-123">레거시 동작 복원</span><span class="sxs-lookup"><span data-stu-id="cd094-123">Restoring legacy behavior</span></span>

<span data-ttu-id="cd094-124">4.7.1부터 시작하는 .NET Framework의 버전을 대상으로 하는 응용 프로그램은 응용 프로그램의 구성 파일의 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 섹션에서 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 스위치를 추가하고 `true`로 해당 값을 설정하여 내게 필요한 옵션 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="cd094-125">예를 들어 다음 구성은 .NET Framework 4.7.2에 도입된 내게 필요한 옵션 기능을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="cd094-126">.NET Framework 4.7.2에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="cd094-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="cd094-127">.NET Framework 4.7.2에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="cd094-128">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd094-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="cd094-129">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="cd094-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a><span data-ttu-id="cd094-130">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd094-130">Windows Forms</span></span>

<span data-ttu-id="cd094-131">**고대비 테마에서 OS 정의 색**</span><span class="sxs-lookup"><span data-stu-id="cd094-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="cd094-132">.NET Framework 4.7.2부터 Windows Forms는 고대비 테마에서 운영 체제에 의해 정의된 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="cd094-133">이는 다음 컨트롤에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-133">This affects the following controls:</span></span>

- <span data-ttu-id="cd094-134"><xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤의 드롭다운 화살표</span><span class="sxs-lookup"><span data-stu-id="cd094-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="cd094-135"><xref:System.Windows.Forms.ButtonBase.FlatStyle>이 <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>으로 설정된 <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd094-136">이전에 선택한 텍스트 및 배경색이 대비되지 않았고 읽기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="cd094-137">해당 <xref:System.Windows.Forms.Control.Enabled> 속성이 `false`로 설정된 <xref:System.Windows.Forms.GroupBox> 내부에 포함된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
 
- <span data-ttu-id="cd094-138">고대비 모드에서 명도 대비를 증가시킨 <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> 및 <xref:System.Windows.Forms.ToolStripDropDownButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="cd094-139"><xref:System.Windows.Forms.DataGridViewLinkCell>의 <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="cd094-140">**내레이터 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="cd094-140">**Narrator improvements**</span></span>

<span data-ttu-id="cd094-141">.NET Framework 4.7.2부터 내레이터 지원이 다음과 같이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="cd094-142"><xref:System.Windows.Forms.ToolStripMenuItem>의 텍스트를 발표할 경우 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> 속성 값도 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span> 

- <span data-ttu-id="cd094-143"><xref:System.Windows.Forms.ToolStripMenuItem>이 해당 <xref:System.Windows.Forms.Control.Enabled> 속성을 `false`로 설정할 때를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="cd094-144"><xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> 속성이 `true`로 설정될 경우 확인란의 상태에 대한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="cd094-145">내레이터의 스캔 모드 포커스 순서는 ClickOnce 다운로드 대화 상자 창에서 컨트롤의 시각적 개체 순서와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="cd094-146">**DataGridView의 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="cd094-146">**DataGridView improvements**</span></span>

<span data-ttu-id="cd094-147">.NET Framework 4.7.2부터 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 다음과 같은 내게 필요한 옵션 개선 사항이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="cd094-148">행은 키보드를 사용하여 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="cd094-149">현재 열로 정렬하기 위해 사용자는 F3 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="cd094-150"><xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType>이 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>으로 설정된 경우 열 헤더는 색을 변경하여 현재 행의 셀을 통해 현재 열을 사용자 탭으로 나타내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="cd094-151"><xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType>의 <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> 속성은 이제 올바른 부모 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="cd094-152">**개선된 시각적 표시**</span><span class="sxs-lookup"><span data-stu-id="cd094-152">**Improved visual cues**</span></span>

- <span data-ttu-id="cd094-153"><xref:System.Windows.Forms.ButtonBase.Text> 속성이 빈 <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.CheckBox> 컨트롤은 포커스를 받을 때 포커스 표시기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="cd094-154">**개선된 속성 표 지원**</span><span class="sxs-lookup"><span data-stu-id="cd094-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="cd094-155"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용하도록 설정한 경우에만 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 속성에 대한 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="cd094-156"><xref:System.Windows.Forms.PropertyGrid> 컨트롤 자식 요소는 PropertyGrid 요소를 사용자가 변경할 수 있는 경우에만 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 속성에 대한 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="cd094-157">**바로 가기 탐색 개선**</span><span class="sxs-lookup"><span data-stu-id="cd094-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="cd094-158"><xref:System.Windows.Forms.ToolStripButton> 컨트롤은 <xref:System.Windows.Forms.ToolStripPanel.TabStop> 속성이 `true`로 설정된 <xref:System.Windows.Forms.ToolStripPanel>에 포함된 경우 포커스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="cd094-159">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="cd094-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="cd094-160">**CheckBox 및 RadioButton 컨트롤에 대한 변경**</span><span class="sxs-lookup"><span data-stu-id="cd094-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="cd094-161">.NET Framework 4.7.1 이전 버전에서 WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> 및 <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> 컨트롤에는 일치하지 않는, 그리고 기본 및 고대비 테마에서는 잘못된 포커스 시각적 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="cd094-162">이러한 문제는 컨트롤에 아무 콘텐츠 집합도 없는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="cd094-163">이렇게 하면 테마 혼동 및 포커스 시각적 개체 간 전환을 보기 어렵게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="cd094-164">NET Framework 4.7.2에서 이러한 시각적 개체는 이제 테마에서 더욱 일관적이고 기본 및 고대비 테마에서 더욱 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="cd094-165">**WPF 응용 프로그램에서 호스트되는 WinForms 컨트롤**</span><span class="sxs-lookup"><span data-stu-id="cd094-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="cd094-166">.NET Framework 4.7.1 이전 버전에서 WPF 응용 프로그램에서 호스트되는 WinForms 컨트롤의 경우 사용자는 해당 계층의 첫 번째 또는 마지막 컨트롤이 WPF <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤인 경우 WinForms 계층을 탭아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="cd094-167">.NET Framework 4.7.2에서 사용자는 이제 WinForms 계층을 탭아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="cd094-168">그러나 WinForms 계층을 이스케이프하지 않는 포커스를 사용하는 자동화된 응용 프로그램은 더 이상 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="cd094-169">.NET Framework 4.7.1에서 내게 필요한 옵션의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="cd094-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="cd094-170">.NET Framework 4.7.1에는 다음과 같은 영역의 새로운 내게 필요한 옵션 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="cd094-171">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="cd094-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="cd094-172">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd094-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="cd094-173">ASP.NET 웹 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="cd094-174">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="cd094-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="cd094-175">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="cd094-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="cd094-176">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="cd094-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="cd094-177">**화면 판독기 개선 사항**</span><span class="sxs-lookup"><span data-stu-id="cd094-177">**Screen reader improvements**</span></span>

<span data-ttu-id="cd094-178">내게 필요한 옵션 개선 사항이 활성화된 경우 .NET Framework 4.7.1에는 화면 판독기에 영향을 주는 다음과 같은 향상 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="cd094-179">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.Expander> 컨트롤은 단추로 화면 판독기에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="cd094-180">.NET Framework 4.7.1부터 확장/축소 가능한 그룹으로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="cd094-181">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 “사용자 지정”으로 화면 판독기에서 공지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="cd094-182">.NET Framework 4.7.1부터 이제 데이터 표 셸(지역화된)로 올바르게 공지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="cd094-183">.NET Framework 4.7.1부터 화면 판독기는 편집 가능한 <xref:System.Windows.Controls.ComboBox>의 이름을 공지합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="cd094-184">.NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.PasswordBox> 컨트롤은 "보기에 항목 없음"으로 공지되었거나 그렇지 않은 경우 잘못된 동작이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="cd094-185">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="cd094-186">**UIAutomation LiveRegion 지원**</span><span class="sxs-lookup"><span data-stu-id="cd094-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="cd094-187">내레이터와 같은 화면 판독기는 사용자가 일반적으로 포커스가 있는 UI 콘텐츠의 텍스트 음성 변환 출력에 의해 응용 프로그램의 UI 콘텐츠를 읽는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="cd094-188">그러나 UI 요소가 변경되고 포커스가 없는 경우 사용자는 알림을 받지 못하고 중요한 정보를 놓칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="cd094-189">라이브 영역은 이 문제를 해결하는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="cd094-190">개발자는 화면 판독기 또는 다른 UIAutomation 클라이언트에게 UI 요소에 중요한 변경 내용이 만들어졌음을 알리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="cd094-191">화면 판독기는 사용자에게 이 변경 내용을 알리는 방법 및 시점을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-191">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="cd094-192">라이브 영역을 지원하기 위해 다음과 같은 API가 WPF에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="cd094-193">**LiveSetting** 속성 및 **LiveRegionChanged** 이벤트를 식별하는 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 필드</span><span class="sxs-lookup"><span data-stu-id="cd094-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="cd094-194">XAML을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="cd094-195">화면 판독기에 사용자에 대한 UI 변경 내용의 중요성을 알리는 **AutomationProperties.LiveSetting** 연결된 속성</span><span class="sxs-lookup"><span data-stu-id="cd094-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="cd094-196">**AutomationProperties.LiveSetting** 연결된 속성을 식별하는 <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="cd094-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="cd094-197">**LiveSetting** 값을 제공하도록 재정의될 수 있는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="cd094-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="cd094-198">**LiveSetting** 값을 가져오고 설정하는 <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 메서드</span><span class="sxs-lookup"><span data-stu-id="cd094-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="cd094-199">다음 가능한 **LiveSetting** 값을 정의하는 <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 열거형</span><span class="sxs-lookup"><span data-stu-id="cd094-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="cd094-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd094-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd094-201">라이브 영역의 콘텐츠가 변경된 경우 요소는 알림을 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-201">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="cd094-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd094-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd094-203">라이브 영역의 콘텐츠가 변경된 경우 요소는 비중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="cd094-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd094-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd094-205">라이브 영역의 콘텐츠가 변경된 경우 요소는 중단 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="cd094-206">다음 예제와 같이 관심 있는 요소에 **AutomationProperties.LiveSetting** 속성을 설정하여 LiveRegion을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="cd094-207">라이브 영역에 있는 데이터가 변경되고 화면 판독기에 알려야 하는 경우 다음 샘플과 같이 명시적으로 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="cd094-208">**고대비**</span><span class="sxs-lookup"><span data-stu-id="cd094-208">**High contrast**</span></span>

<span data-ttu-id="cd094-209">.NET Framework 4.7.1부터 다양한 WPF 컨트롤에 고대비의 개선 사항이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="cd094-210"><xref:System.Windows.SystemParameters.HighContrast%2A> 테마가 설정된 경우 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="cd094-211">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-211">These include:</span></span>

- <span data-ttu-id="cd094-212"><xref:System.Windows.Controls.Expander> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="cd094-213"><xref:System.Windows.Controls.Expander> 컨트롤에 대한 포커스 시각적 개체는 이제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="cd094-214"><xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤에 대한 키보드 시각적 개체도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="cd094-215">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-215">For example:</span></span>

    <span data-ttu-id="cd094-216">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-216">Before:</span></span> 
    
    ![내게 필요한 옵션 개선 사항 이전의 포커스가 있는 Expander 컨트롤](media/expander-before.png)

    <span data-ttu-id="cd094-218">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-218">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 포커스가 있는 Expander 컨트롤](media/expander-after.png)

- <span data-ttu-id="cd094-220"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="cd094-221"><xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤의 텍스트는 이제 고대비 테마에서 선택하면 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="cd094-222">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-222">For example:</span></span>

    <span data-ttu-id="cd094-223">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-223">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 포커스가 있는 고대비 라디오 단추](media/radio-button-before.png)
    
    <span data-ttu-id="cd094-225">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-225">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 포커스가 있는 고대비 라디오 단추](media/radio-button-after.png)

- <span data-ttu-id="cd094-227"><xref:System.Windows.Controls.ComboBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-227"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="cd094-228">.NET Framework 4.7.1부터 비활성화된 <xref:System.Windows.Controls.ComboBox> 컨트롤의 테두리는 비활성화된 텍스트와 동일한 색입니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="cd094-229">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-229">For example:</span></span>
    
    <span data-ttu-id="cd094-230">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-230">Before:</span></span> 

     ![내게 필요한 옵션 개선 사항 이전의 콤보 상자 비활성화된 테두리 및 텍스트](media/combo-disabled-before.png)

    <span data-ttu-id="cd094-232">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-232">After:</span></span>   

     ![내게 필요한 옵션 개선 사항 이후의 콤보 상자 비활성화된 테두리 및 텍스트](media/combo-disabled-after.png)

    <span data-ttu-id="cd094-234">또한 비활성화되고 포커스가 있는 단추는 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="cd094-235">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-235">Before:</span></span>

    ![내게 필요한 옵션 개선 사항 이전의 단추 테마 색](media/button-themes-before.png) 
    
    <span data-ttu-id="cd094-237">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-237">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 단추 테마 색](media/button-themes-after.png) 

    <span data-ttu-id="cd094-239">마지막으로 .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일을 `Toolbar.ComboBoxStyleKey`로 설정하면 드롭다운 화살표가 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="cd094-240">이 문제는 .NET Framework 4.7.1부터 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="cd094-241">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-241">For example:</span></span>

    <span data-ttu-id="cd094-242">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-242">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="cd094-244">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-244">After:</span></span> 

    ![내게 필요한 옵션 개선 사항 이후의 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <span data-ttu-id="cd094-246"><xref:System.Windows.Controls.DataGrid> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="cd094-247">.NET Framework 4.7.1부터 <xref:System.Windows.Controls.DataGrid> 컨트롤의 정렬 표시기 화살표는 이제 올바른 테마 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="cd094-248">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-248">For example:</span></span>

    <span data-ttu-id="cd094-249">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-249">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 정렬 표시기 화살표](media/sort-indicator-before.png) 
    
    <span data-ttu-id="cd094-251">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-251">After:</span></span>   
 
    ![내게 필요한 옵션 개선 사항 이후의 정렬 표시기 화살표](media/sort-indicator-after.png) 
    
    <span data-ttu-id="cd094-253">또한 .NET Framework 4.7 이전 버전에서 기본 링크 스타일은 고대비 모드의 마우스에서 잘못된 색으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="cd094-254">이는 .NET Framework 4.7.1부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="cd094-255">마찬가지로 <xref:System.Windows.Controls.DataGrid> 확인란 열은 .NET Framework 4.7.1부터 키보드 포커스 피드백에 대해 예상되는 색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="cd094-256">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-256">Before:</span></span> 

    ![내게 필요한 옵션 개선 사항 이전의 DataGrid 기본 링크 스타일](media/default-link-style-before.png) 
 
    <span data-ttu-id="cd094-258">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-258">After:</span></span>    
  
    ![내게 필요한 옵션 개선 사항 이후의 DataGrid 기본 링크 스타일](media/default-link-style-after.png)  

<span data-ttu-id="cd094-260">.NET Framework 4.7.1에서 WPF 내게 필요한 옵션 개선 사항에 대한 자세한 내용은 [WPF의 내게 필요한 옵션 개선 사항](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd094-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>
## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="cd094-261">Windows Forms 내게 필요한 옵션 개선 사항</span><span class="sxs-lookup"><span data-stu-id="cd094-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="cd094-262">.NET Framework 4.7.1에서 WinForms(Windows Forms)는 다음 영역에서 내게 필요한 옵션 변경 내용을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="cd094-263">**고대비 모드에서 향상된 표시**</span><span class="sxs-lookup"><span data-stu-id="cd094-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="cd094-264">.NET Framework 4.7.1부터 다양한 WinForms 컨트롤은 운영 체제에서 사용할 수 있는 고대비 모드의 향상된 렌더링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="cd094-265">Windows 10은 일부 고대비 시스템 색에 대한 값을 변경했으며 Windows Forms는 Windows 10 Win32 프레임워크를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="cd094-266">최상의 환경을 위해 최신 버전의 Windows를 실행하고 테스트 응용 프로그램에 app.manifest 파일을 추가하여 최신 OS로 옵트인하고 다음과 같이 보이도록 Windows 10 지원되는 OS 줄에 대한 주석을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="cd094-267">고대비 변경 내용의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="cd094-268"><xref:System.Windows.Forms.MenuStrip> 항목의 확인 표시는 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="cd094-269">선택하면 비활성화된 <xref:System.Windows.Forms.MenuStrip> 항목이 보기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="cd094-270">선택된 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 선택 영역 색과 대비됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="cd094-271">비활성화된 텍스트는 읽기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-271">Disabled text is easier to read.</span></span> <span data-ttu-id="cd094-272">예:</span><span class="sxs-lookup"><span data-stu-id="cd094-272">For example:</span></span>

    <span data-ttu-id="cd094-273">이전:</span><span class="sxs-lookup"><span data-stu-id="cd094-273">Before:</span></span>

    ![내게 필요한 옵션 개선 사항 이전의 비활성화된 텍스트](media/wf-disabled-before.png) 

    <span data-ttu-id="cd094-275">이후:</span><span class="sxs-lookup"><span data-stu-id="cd094-275">After:</span></span>

    ![내게 필요한 옵션 개선 사항 이후의 비활성화된 텍스트](media/wf-disabled-after.png) 

- <span data-ttu-id="cd094-277">스레드 예외 대화 상자의 고대비 개선 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="cd094-278">**향상된 내레이터 지원**</span><span class="sxs-lookup"><span data-stu-id="cd094-278">**Improved Narrator support**</span></span>

<span data-ttu-id="cd094-279">.NET Framework 4.7.1에서 Windows Forms는 내레이터에 대한 다음과 같은 내게 필요한 옵션 개선 사항을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="cd094-280"><xref:System.Windows.Forms.MonthCalendar> 컨트롤은 내레이터 및 다른 UI 자동화 도구로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="cd094-281"><xref:System.Windows.Forms.CheckedListBox> 컨트롤은 항목의 선택 상태가 변경되어 목록 항목의 값을 변경했음을 사용자에게 알릴 때 내레이터에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="cd094-282"><xref:System.Windows.Forms.DataGridViewCell> 컨트롤은 올바른 읽기 전용 상태를 내레이터에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="cd094-283">내레이터는 이제 비활성화된 <xref:System.Windows.Forms.ToolStripMenuItem> 텍스트를 읽을 수 있는 반면 이전에는 비활성화된 메뉴 항목을 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="cd094-284">**UIAutomation 내게 필요한 옵션 패턴에 대한 향상된 지원**</span><span class="sxs-lookup"><span data-stu-id="cd094-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="cd094-285">.NET Framework 4.7.1부터 내게 필요한 옵션 기술 도구의 개발자는 API 내게 필요한 옵션의 일반 패턴 및 여러 WinForms 컨트롤에 대한 속성을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="cd094-286">이러한 내게 필요한 옵션 개선 사항은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="cd094-287"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ToolStripSplitButton>은 이제 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="cd094-288"><xref:System.Windows.Forms.DataGridViewCheckBoxCell>은 이제 [토글 패턴](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="cd094-289"><xref:System.Windows.Forms.ToolStripItem> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성 및 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="cd094-290"><xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="cd094-291">**향상된 속성 브라우저 환경**</span><span class="sxs-lookup"><span data-stu-id="cd094-291">**Improved property browser experience**</span></span>

<span data-ttu-id="cd094-292">.NET Framework 4.7.1부터 Windows Forms는 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="cd094-293">다양한 드롭다운 선택 창을 통한 향상된 키보드 탐색</span><span class="sxs-lookup"><span data-stu-id="cd094-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="cd094-294">불필요한 탭 정지의 감소</span><span class="sxs-lookup"><span data-stu-id="cd094-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="cd094-295">컨트롤 형식의 향상된 보고</span><span class="sxs-lookup"><span data-stu-id="cd094-295">Better reporting of control types.</span></span>
- <span data-ttu-id="cd094-296">향상된 내레이터 동작</span><span class="sxs-lookup"><span data-stu-id="cd094-296">Improved narrator behavior.</span></span>
 
<a name="aspnet471"></a>
## <a name="aspnet-web-controls"></a><span data-ttu-id="cd094-297">ASP.NET 웹 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd094-297">ASP.NET web controls</span></span>

<span data-ttu-id="cd094-298">.NET Framework 4.7.1 및 Visual Studio 2017 15.3부터 ASP.NET은 ASP.NET 웹 컨트롤이 Visual Studio의 내게 필요한 옵션 기술과 연동하는 방식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="cd094-299">변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-299">Changes include the following:</span></span>

- <span data-ttu-id="cd094-300">**자세히 보기** 마법사의 **필드 추가** 대화 상자 또는 **ListView** 마법사의 **ListView 구성** 대화 상자와 같이 컨트롤에서 누락된 UI 액세스 가능성 패턴을 구현하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="cd094-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="cd094-301">**데이터 호출기 필드 편집기**와 같이 고대비 모드에서 디스플레이를 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="cd094-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="cd094-302">DataPager 컨트롤의 **호출기 필드 편집** 마법사의 **필드** 대화 상자, **ObjectContext 구성** 대화 상자 또는 **데이터 원본 구성** 마법사의 **데이터 선택 구성** 대화 상자와 같은 컨트롤의 키보드 탐색 환경을 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="cd094-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>
## <a name="net-sdk-tools"></a><span data-ttu-id="cd094-303">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="cd094-303">.NET SDK Tools</span></span>

<span data-ttu-id="cd094-304">[Configuration Editor 도구(SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) 및 [Service Trace Viewer 도구(SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md)는 다양한 액세스 가능성 문제를 수정하여 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="cd094-305">이들 중 대부분은 정의되지 않은 이름이나 특정 UI 자동화 패턴이 올바르게 구현되지 않은 것과 같은 사소한 문제였습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="cd094-306">많은 사용자가 이러한 잘못된 값을 인식하지 못하지만, 화면 판독기와 같은 보조 기술을 사용하는 고객은 이러한 SDK 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> 

<span data-ttu-id="cd094-307">이러한 개선 사항은 키보드 포커스 순서 등의 일부 이전 동작을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>
## <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="cd094-308">Windows WF(Workflow Foundation) 워크플로 디자이너</span><span class="sxs-lookup"><span data-stu-id="cd094-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="cd094-309">워크플로 디자이너에서 내게 필요한 옵션 변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="cd094-310">일부 컨트롤에서 왼쪽에서 오른쪽으로, 위쪽에서 아래쪽으로 탭 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="cd094-311"><xref:System.ServiceModel.Activities.InitializeCorrelation> 작업에 대한 상관 관계 데이터를 설정하는 초기화 상관 관계 창</span><span class="sxs-lookup"><span data-stu-id="cd094-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="cd094-312"><xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 작업에 대한 콘텐츠 정의 창</span><span class="sxs-lookup"><span data-stu-id="cd094-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="cd094-313">바로 가기를 통해 추가 함수가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="cd094-314">작업의 속성을 편집할 때 처음으로 포커스된 경우 바로 가기에서 속성 그룹을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="cd094-315">경고 아이콘은 바로 가기에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="cd094-316">바로 가기에서 **속성** 창의 **추가 속성** 단추에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="cd094-317">바로 가기 사용자는 워크플로 디자이너의 **인수** 및 **변수** 창에 있는 헤더 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="cd094-318">다음과 같은 경우 포커스가 있는 항목의 표시 유형 향상</span><span class="sxs-lookup"><span data-stu-id="cd094-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="cd094-319">워크플로 디자이너 및 작업 디자이너에서 사용하는 데이터 그리드에 행 추가</span><span class="sxs-lookup"><span data-stu-id="cd094-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="cd094-320"><xref:System.ServiceModel.Activities.ReceiveReply> 및 <xref:System.ServiceModel.Activities.SendReply> 작업에서 필드 누름</span><span class="sxs-lookup"><span data-stu-id="cd094-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="cd094-321">변수 또는 인수에 대한 기본값 설정</span><span class="sxs-lookup"><span data-stu-id="cd094-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="cd094-322">이제 화면 읽기 프로그램이 다음 항목을 올바르게 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="cd094-323">워크플로 디자이너에서 설정된 중단점</span><span class="sxs-lookup"><span data-stu-id="cd094-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="cd094-324"><xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> 및 <xref:System.ServiceModel.Activities.CorrelationScope> 작업</span><span class="sxs-lookup"><span data-stu-id="cd094-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="cd094-325"><xref:System.ServiceModel.Activities.Receive> 작업의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="cd094-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="cd094-326"><xref:System.Activities.Statements.InvokeMethod> 작업의 대상 유형</span><span class="sxs-lookup"><span data-stu-id="cd094-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="cd094-327"><xref:System.Activities.Statements.TryCatch> 작업의 예외 콤보 상자 및 마지막 섹션</span><span class="sxs-lookup"><span data-stu-id="cd094-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="cd094-328">메시지 유형 콤보 상자, 상관 관계 이니셜라이저 추가 창의 분할기, 콘텐츠 정의 창 및 메시징 작업의 CorrelatesOn 정의 창(<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)</span><span class="sxs-lookup"><span data-stu-id="cd094-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="cd094-329">상태 컴퓨터 전환 및 전환 대상</span><span class="sxs-lookup"><span data-stu-id="cd094-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="cd094-330"><xref:System.Activities.Statements.FlowDecision> 작업의 주석 및 커넥터</span><span class="sxs-lookup"><span data-stu-id="cd094-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="cd094-331">작업의 팝업(마우스 오른쪽 단추 클릭) 메뉴</span><span class="sxs-lookup"><span data-stu-id="cd094-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="cd094-332">속성 값 편집기, 검색 정리 단추, 범주별으로 및 사전순 정렬 단추 및 속성 그리드의 식 편집기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="cd094-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="cd094-333">워크플로 디자이너의 확대/축소 백분율</span><span class="sxs-lookup"><span data-stu-id="cd094-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="cd094-334"><xref:System.Activities.Statements.Parallel> 및 <xref:System.Activities.Statements.Pick> 작업의 구분 기호</span><span class="sxs-lookup"><span data-stu-id="cd094-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="cd094-335"><xref:System.Activities.Statements.InvokeDelegate> 작업</span><span class="sxs-lookup"><span data-stu-id="cd094-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="cd094-336">사전 작업의 형식 선택 창(`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`등)</span><span class="sxs-lookup"><span data-stu-id="cd094-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="cd094-337">.NET 형식 찾아보기 및 선택 창</span><span class="sxs-lookup"><span data-stu-id="cd094-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="cd094-338">워크플로 디자이너의 이동 경로</span><span class="sxs-lookup"><span data-stu-id="cd094-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="cd094-339">고대비 테마를 선택한 사용자는 워크플로 디자이너의 표시 유형에서 여러 개선 사항 및 포커스 요소에 사용되는 요소와 더욱 분명한 선택 영역 상자 사이의 대조율과 같은 해당 컨트롤을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cd094-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd094-340">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd094-340">See Also</span></span>

[<span data-ttu-id="cd094-341">.NET Framework의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="cd094-341">What's new in the .NET Framework</span></span>](whats-new.md)
 
