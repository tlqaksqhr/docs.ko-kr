---
title: "Windows Forms의 높은 DPI 지원"
ms.custom: 
ms.date: 05/16/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a68c9278d4e8092be5c744109e56f7cb52498095
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="ca155-102">Windows Forms의 높은 DPI 지원</span><span class="sxs-lookup"><span data-stu-id="ca155-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="ca155-103">.NET Framework 4.7 이상에서는 Windows Forms 일반적인 높은 DPI 및 동적 DPI 시나리오에 대 한 향상 된 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="ca155-104">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-104">These include:</span></span> 

- <span data-ttu-id="ca155-105">와 같은 확장 및 레이아웃의 다양 한 Windows Forms의 향상 된 컨트롤의 <xref:System.Windows.Forms.MonthCalendar> 제어 및 <xref:System.Windows.Forms.CheckedListBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

- <span data-ttu-id="ca155-106">한 번 통과 크기 조정</span><span class="sxs-lookup"><span data-stu-id="ca155-106">Single-pass scaling.</span></span>  <span data-ttu-id="ca155-107">.NET Framework 4.6 및 이전 버전에서는 크기 조정 필요 이상 인해 일부 컨트롤 크기를 조정할 수 있는 여러 과정을 통해 수행할 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="ca155-108">사용자가 변경한 DPI 또는 배율 인수는 Windows Forms 응용 프로그램 시작 된 후 동적 DPI 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="ca155-109">.NET Framework 4.7 부터는.NET Framework의 버전에서는 향상 된 높은 DPI 지원 옵트인 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="ca155-110">활용 하도록 응용 프로그램을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="ca155-111">높은 DPI 지원에 대 한 Windows Forms 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="ca155-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="ca155-112">높은 DPI 인식 지원는 새 Windows Forms 기능은 Windows 10 작성자가 업데이트를 시작 하는 Windows 운영 체제에서 실행 되 고.NET Framework 4.7 대상으로 하는 응용 프로그램 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span> 

<span data-ttu-id="ca155-113">또한 Windows Forms 응용 프로그램의 높은 DPI 지원을 구성 하는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="ca155-114">Windows 10와의 호환성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="ca155-115">이 작업을 수행 하려면 매니페스트 파일에 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.comn:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="ca155-116">당 모니터 DPI 인식 사용의 *app.config* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="ca155-117">Windows Forms 탑재 되었습니다 [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) 요소를 새 기능을 추가 하는 사용자 지정.NET Framework 4.7부터 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../docs/framework/configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="ca155-118">높은 DPI를 지 원하는 새 기능을 이용 하려면 다음 응용 프로그램 구성 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > <span data-ttu-id="ca155-119">.NET Framework의 이전 버전에서는 높은 DPI 지원을 추가 하려면 매니페스트를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="ca155-120">App.config 파일에 정의 된 설정을 재정의 하므로이 방법은 더 이상 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>
   
- <span data-ttu-id="ca155-121">정적 호출 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ca155-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>
   
  <span data-ttu-id="ca155-122">이 프로그램 응용 프로그램 진입점에서 첫 번째 메서드 호출 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="ca155-123">예:</span><span class="sxs-lookup"><span data-stu-id="ca155-123">For example:</span></span>
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="ca155-124">개별 높은 DPI 기능을 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="ca155-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="ca155-125">설정의 `DpiAwareness` 값을 `PerMonitorV2` .NET Framework 4.7 부터는.NET Framework 버전에서 지 원하는 모든 높은 DPI 인식 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="ca155-126">일반적으로이 대부분의 Windows Forms 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="ca155-127">그러나 다음 하나 이상의 개별 기능을 옵트아웃 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="ca155-128">이 작업을 위한 가장 중요 한 이유는 기존 응용 프로그램 코드 이미 해당 기능을 처리 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="ca155-129">예를 들어 응용 프로그램에서 자동 크기 조정를 처리 하는 경우 다음과 같이 자동 크기 조정 기능을 비활성화 하 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

<span data-ttu-id="ca155-130">개별 키와 값의 목록에 대 한 참조 [Windows Forms 구성 요소 추가](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="ca155-131">새 DPI 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="ca155-131">New DPI change events</span></span>

<span data-ttu-id="ca155-132">3 개의 새 이벤트를.NET Framework 4.7 이상에서는 동적 DPI 변경 내용을 프로그래밍 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="ca155-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>부모 컨트롤에 대 한 DPI 변경 이벤트가 발생 한 후 컨트롤에 대 한 DPI 설정을 프로그래밍 방식으로 변경 되거나 형식 발생 때 발생 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="ca155-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>부모 컨트롤에 대 한 DPI 변경 이벤트 이전에 컨트롤에 대 한 DPI 설정을 프로그래밍 방식으로 변경 되거나 형식 발생 했습니다 때 발생 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="ca155-135"><xref:System.Windows.Forms.Form.DpiChanged>DPI 설정을 폼이 표시 현재 디스플레이 장치에서 변경 될 때 발생입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="ca155-136">새 도우미 메서드 및 속성</span><span class="sxs-lookup"><span data-stu-id="ca155-136">New helper methods and properties</span></span>

<span data-ttu-id="ca155-137">또한.NET Framework 4.7 다양 한 DPI 조정 하는 방법에 대 한 정보를 제공 하 고 DPI 조정 수행할 수 있도록 하는 새로운 도우미 메서드 및 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="ca155-138">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-138">These include:</span></span>

- <span data-ttu-id="ca155-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>를 논리적 좌표에서 값을 장치 픽셀을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="ca155-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>를 장치에 대 한 논리 DPI 비트맵 이미지의 크기를 조정입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="ca155-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>를 반환 하는 현재 장치에 대 한 DPI입니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="ca155-142">버전 관리 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ca155-142">Versioning considerations</span></span>

<span data-ttu-id="ca155-143">를.NET Framework 4.7 및 Windows 10 작성자 업데이트에서 실행 하는 것 외에도 없으면 높은 DPI 개선와 호환 되는 환경에서 응용 프로그램 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="ca155-144">이 경우 응용 프로그램에 대 한 대체 (fallback)를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="ca155-145">수행 하려면이 옵션을 수행할 수 있습니다 [사용자 지정 그리기](./controls/user-drawn-controls.md) 크기 조정을 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="ca155-146">이 위해 응용 프로그램 실행 되는 운영 체제를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="ca155-147">다음과 같은 코드로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="ca155-148">참고 응용 프로그램이 응용 프로그램 매니페스트에서 지원 되는 운영 체제로 나열 되지 않은 경우 Windows 10 감지 성공적으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="ca155-149">또한 응용 프로그램을 빌드한.NET Framework의 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="ca155-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca155-150">See also</span></span>

[<span data-ttu-id="ca155-151">Windows Forms 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca155-151">Windows Forms Add Configuration Element</span></span>](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[<span data-ttu-id="ca155-152">Windows Forms의 크기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="ca155-152">Adjusting the Size and Scale of Windows Forms</span></span>](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
