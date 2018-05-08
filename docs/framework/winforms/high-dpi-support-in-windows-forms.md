---
title: Windows Forms의 높은 DPI 지원
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a085658579c8cd3ba43fd07a7816581e03c3d64a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="high-dpi-support-in-windows-forms"></a>Windows Forms의 높은 DPI 지원

.NET Framework 4.7 이상에서는 Windows Forms 일반적인 높은 DPI 및 동적 DPI 시나리오에 대 한 향상 된 기능을 포함 합니다. 여기에는 다음이 포함됩니다. 

- 와 같은 확장 및 레이아웃의 다양 한 Windows Forms의 향상 된 컨트롤의 <xref:System.Windows.Forms.MonthCalendar> 제어 및 <xref:System.Windows.Forms.CheckedListBox> 제어 합니다. 

- 한 번 통과 크기 조정  .NET Framework 4.6 및 이전 버전에서는 크기 조정 필요 이상 인해 일부 컨트롤 크기를 조정할 수 있는 여러 과정을 통해 수행할 되었습니다.

- 사용자가 변경한 DPI 또는 배율 인수는 Windows Forms 응용 프로그램 시작 된 후 동적 DPI 시나리오를 지원 합니다.

.NET Framework 4.7 부터는.NET Framework의 버전에서는 향상 된 높은 DPI 지원 옵트인 기능입니다. 활용 하도록 응용 프로그램을 구성 해야 합니다.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>높은 DPI 지원에 대 한 Windows Forms 응용 프로그램 구성

높은 DPI 인식 지원는 새 Windows Forms 기능은 Windows 10 작성자가 업데이트를 시작 하는 Windows 운영 체제에서 실행 되 고.NET Framework 4.7 대상으로 하는 응용 프로그램 에서만 사용할 수 있습니다. 

또한 Windows Forms 응용 프로그램의 높은 DPI 지원을 구성 하는 다음을 수행 해야 합니다.

- Windows 10와의 호환성을 선언 합니다.

  이 작업을 수행 하려면 매니페스트 파일에 다음을 추가 합니다.

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.comn:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- 당 모니터 DPI 인식 사용의 *app.config* 파일입니다.

  Windows Forms 탑재 되었습니다 [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) 요소를 새 기능을 추가 하는 사용자 지정.NET Framework 4.7부터 지원 합니다. 높은 DPI를 지 원하는 새 기능을 이용 하려면 다음 응용 프로그램 구성 파일을 추가 합니다.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > .NET Framework의 이전 버전에서는 높은 DPI 지원을 추가 하려면 매니페스트를 사용 했습니다. App.config 파일에 정의 된 설정을 재정의 하므로이 방법은 더 이상 권장 됩니다.
   
- 정적 호출 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.
   
  이 프로그램 응용 프로그램 진입점에서 첫 번째 메서드 호출 이어야 합니다. 예를 들어:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>개별 높은 DPI 기능을 옵트아웃

설정의 `DpiAwareness` 값을 `PerMonitorV2` .NET Framework 4.7 부터는.NET Framework 버전에서 지 원하는 모든 높은 DPI 인식 기능을 사용할 수 있습니다. 일반적으로이 대부분의 Windows Forms 응용 프로그램에 적합 합니다. 그러나 다음 하나 이상의 개별 기능을 옵트아웃 하는 것이 좋습니다. 이 작업을 위한 가장 중요 한 이유는 기존 응용 프로그램 코드 이미 해당 기능을 처리 하는입니다.  예를 들어 응용 프로그램에서 자동 크기 조정를 처리 하는 경우 다음과 같이 자동 크기 조정 기능을 비활성화 하 하는 경우가 있습니다.

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

개별 키와 값의 목록에 대 한 참조 [Windows Forms 구성 요소 추가](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)합니다.

## <a name="new-dpi-change-events"></a>새 DPI 변경 이벤트

3 개의 새 이벤트를.NET Framework 4.7 이상에서는 동적 DPI 변경 내용을 프로그래밍 방식으로 처리할 수 있습니다.

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>부모 컨트롤에 대 한 DPI 변경 이벤트가 발생 한 후 컨트롤에 대 한 DPI 설정을 프로그래밍 방식으로 변경 되거나 형식 발생 때 발생 하는입니다.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>부모 컨트롤에 대 한 DPI 변경 이벤트 이전에 컨트롤에 대 한 DPI 설정을 프로그래밍 방식으로 변경 되거나 형식 발생 했습니다 때 발생 하는입니다.
- <xref:System.Windows.Forms.Form.DpiChanged>DPI 설정을 폼이 표시 현재 디스플레이 장치에서 변경 될 때 발생입니다.

## <a name="new-helper-methods-and-properties"></a>새 도우미 메서드 및 속성

또한.NET Framework 4.7 다양 한 DPI 조정 하는 방법에 대 한 정보를 제공 하 고 DPI 조정 수행할 수 있도록 하는 새로운 도우미 메서드 및 속성을 추가 합니다. 여기에는 다음이 포함됩니다.

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>를 논리적 좌표에서 값을 장치 픽셀을 변환 합니다.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>를 장치에 대 한 논리 DPI 비트맵 이미지의 크기를 조정입니다.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>를 반환 하는 현재 장치에 대 한 DPI입니다.

## <a name="versioning-considerations"></a>버전 관리 고려 사항

를.NET Framework 4.7 및 Windows 10 작성자 업데이트에서 실행 하는 것 외에도 없으면 높은 DPI 개선와 호환 되는 환경에서 응용 프로그램 실행할 수도 있습니다. 이 경우 응용 프로그램에 대 한 대체 (fallback)를 개발 해야 합니다. 수행 하려면이 옵션을 수행할 수 있습니다 [사용자 지정 그리기](./controls/user-drawn-controls.md) 크기 조정을 처리 하도록 합니다.

이 위해 응용 프로그램 실행 되는 운영 체제를 확인 해야 합니다. 다음과 같은 코드로 수행할 수 있습니다.

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

참고 응용 프로그램이 응용 프로그램 매니페스트에서 지원 되는 운영 체제로 나열 되지 않은 경우 Windows 10 감지 성공적으로 하지 않습니다.

또한 응용 프로그램을 빌드한.NET Framework의 버전을 확인할 수 있습니다.

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>참고자료

[Windows Forms 구성 요소를 추가합니다.](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[Windows Forms의 크기 및 배율 조정](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
