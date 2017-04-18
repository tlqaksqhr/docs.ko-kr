---
title: "WPF 및 Direct3D9 상호 운용성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9[WPF 상호 운용성], Direct3D9 콘텐츠 만들기"
  - "WPF, Direct3D9 콘텐츠 만들기"
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# WPF 및 Direct3D9 상호 운용성
Direct3D9 콘텐츠를 WPF\(Windows Presentation Foundation\) 응용 프로그램에 포함할 수 있습니다.  이 항목에서는 WPF와 효율적으로 상호 운용될 수 있도록 Direct3D9 콘텐츠를 만드는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  WPF에서 Direct3D9 콘텐츠를 사용할 때는 성능을 고려해야 합니다.  성능을 최적화하는 방법에 대한 자세한 내용은 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)을 참조하십시오.  
  
## 디스플레이 버퍼  
 <xref:System.Windows.Interop.D3DImage> 클래스는 *백 버퍼*와 *프런트 버퍼*라고 하는 두 가지 디스플레이 버퍼를 관리합니다.  백 버퍼는 Direct3D9 화면입니다.  <xref:System.Windows.Interop.D3DImage.Unlock%2A> 메서드를 호출하면 백 버퍼에 대한 변경 내용이 프런트 버퍼에 복사됩니다.  
  
 다음 그림에서는 백 버퍼와 프런트 버퍼의 관계를 보여 줍니다.  
  
 ![D3DImage 디스플레이 버퍼](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage\_buffers")  
  
## Direct3D9 장치 만들기  
 Direct3D9 콘텐츠를 렌더링하려면 Direct3D9 장치를 만들어야 합니다.  장치를 만들 때는 두 가지 Direct3D9 개체, 즉 `IDirect3D9`와 `IDirect3D9Ex`를 사용할 수 있습니다.  이러한 개체를 사용하여 `IDirect3DDevice9` 및 `IDirect3DDevice9Ex` 장치를 각각 만듭니다.  
  
 다음 메서드 중 하나를 호출하여 장치를 만듭니다.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 Windows Vista 또는 운영 체제에서 사용 하는 `Direct3DCreate9Ex` 메서드는 Windows 표시 드라이버 모델 \(WDDM\) 사용 하도록 구성 되어 있는 디스플레이.  `Direct3DCreate9` 메서드는 그 이외의 모든 플랫폼에서 사용합니다.  
  
### Direct3DCreate9Ex 메서드의 가용성  
 D3d9.dll을가 `Direct3DCreate9Ex` 메서드를 운영 체제 또는 Windows Vista에만.  이 기능을 Windows XP에서 직접 연결하면 응용 프로그램이 로드되지 않습니다.  `Direct3DCreate9Ex` 메서드가 지원되는지 여부를 확인하려면 DLL을 로드한 후 프로시저 주소를 찾아보십시오.  다음 코드에서는 `Direct3DCreate9Ex` 메서드를 테스트하는 방법을 보여 줍니다.  전체 코드 예제는 [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)를 참조하십시오.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### HWND 만들기  
 장치를 만들려면 HWND가 필요합니다.  대개는 Direct3D9에 사용할 더미 HWND를 만듭니다.  다음 코드 예제에서는 더미 HWND를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### Present 매개 변수  
 장치를 만들려면 `D3DPRESENT_PARAMETERS` 구조체도 필요한데 그 중 몇 가지 매개 변수가 중요합니다.  이러한 매개 변수는 메모리 공간을 최소화하기 위해 선택합니다.  
  
 `BackBufferHeight` 및 `BackBufferWidth` 필드를 1로 설정합니다.  값을 0으로 설정하면 HWND의 크기로 설정됩니다.  
  
 Direct3D9에서 사용하는 메모리의 손상을 방지하고 Direct3D9로 인해 FPU 설정이 변경되지 않도록 `D3DCREATE_MULTITHREADED` 및 `D3DCREATE_FPU_PRESERVE` 플래그를 항상 설정해야 합니다.  
  
 다음 코드 예제에서는 `D3DPRESENT_PARAMETERS` 구조체를 초기화하는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## 백 버퍼 렌더링 대상 만들기  
 Direct3D9 콘텐츠를 <xref:System.Windows.Interop.D3DImage>에 표시하려면 Direct3D9 화면을 만든 후 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드를 호출하여 할당합니다.  
  
### 어댑터 지원 확인  
 화면을 만들기 전에, 필요한 모든 화면 속성이 모든 어댑터에서 지원되는지 확인합니다.  어댑터 하나에만 렌더링하더라도 WPF 창은 시스템에 있는 모든 어댑터에 표시될 수 있습니다.  WPF는 사용 가능한 어댑터 간에 화면을 이동할 수 있기 때문에 항상 다중 어댑터 구성을 처리할 수 있도록 Direct3D9 코드를 작성하고 모든 어댑터에서 지원되는지 여부를 확인해야 합니다.  
  
 다음 코드 예제에서는 시스템의 모든 어댑터에서 Direct3D9가 지원되는지 여부를 확인하는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### 화면 만들기  
 화면을 만들기 전에 대상 운영 체제에서 장치 기능이 좋은 성능을 발휘할 수 있는지 검증해야 합니다.  자세한 내용은 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)을 참조하십시오.  
  
 장치 기능이 검증된 후에는 화면을 만들 수 있습니다.  다음 코드 예제에서는 렌더링 대상을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### WDDM  
 Windows Vista 및 WDDM을 사용 하도록 구성 된 이상 운영 체제에서 렌더링 대상 질감을 만들 고 수준 0 표면에 전달 된 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드.  Windows XP에서는 잠글 수 있는 렌더링 대상 질감을 만들 수 없고 성능이 떨어지기 때문에 이 방법을 사용하지 않는 것이 좋습니다.  
  
## 장치 상태 처리  
 <xref:System.Windows.Interop.D3DImage> 클래스는 *백 버퍼*와 *프런트 버퍼*라고 하는 두 가지 디스플레이 버퍼를 관리합니다.  백 버퍼는 Direct3D 화면입니다.  변경 내용을 백 버퍼에 복사 됩니다 앞으로 프런트 버퍼에 전화를 할 경우는 <xref:System.Windows.Interop.D3DImage.Unlock%2A> 하드웨어에서 표시 되는 메서드를.  경우에 따라 프런트 버퍼를 사용할 수 없습니다.  이와 같이 가용성이 부족해지는 것은 화면 잠금, 전체 화면 전용 Direct3D 응용 프로그램, 사용자 전환 또는 기타 시스템 작업 때문일 수 있습니다.  이 문제가 발생 하면 WPF 응용 프로그램에서 처리 받습니다는 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> 이벤트.  프런트 버퍼에 사용할 수 없게 되 고 응용 프로그램이 응답 하는 방법을 WPF 소프트웨어 렌더링으로 폴백 활성화 됩니다 여부에 따라 달라 집니다.  <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드는 WPF 소프트웨어 렌더링으로 다시 속하는지 여부를 지정 하는 매개 변수를 사용 하는 오버 로드가 있습니다.  
  
 호출 하면는 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> 오버 로드 또는 호출는 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> 와 오버 로드는 `enableSoftwareFallback` 매개 변수를 설정 `false`, 렌더링 시스템 프런트 버퍼를 사용할 수 없을 때 아무것도 표시 되지 않음 백 버퍼에 대 한 참조를 해제.  프런트 버퍼는 다시 사용할 수 있을 때 렌더링 시스템 발생의 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> WPF 응용 프로그램에 알리기 위해 이벤트.  이벤트 처리기를 만들 수 있습니다는 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> 이벤트를 렌더링 하는 올바른 Direct3D 화면을 다시 다시 시작 합니다.  렌더링을 다시 시작 하 여 호출 해야 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 호출 하면는 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> 와 오버 로드는 `enableSoftwareFallback` 매개 변수를 설정 `true`, 호출 하지 않아도 되므로 프런트 버퍼를 사용할 수 없을 때 렌더링 시스템 백 버퍼에 대 한 참조를 유지 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 프런트 버퍼 때 사용할 수 있는 다시.  
  
 소프트웨어 렌더링을 사용 하면 렌더링 시스템 Direct3D 화면에 대 한 참조를 유지 하지만 위치 사용자의 장치를 사용할 수 없을 경우 있을 수 있습니다.  Direct3D9 장치를 사용할 수 있는지 여부를 확인 하기 위해 호출 된 `TestCooperativeLevel` 메서드.  Direct3D9Ex 장치 호출을 확인 하는 `CheckDeviceState` 메서드를 때문에 `TestCooperativeLevel` 메서드는 사용 되지 않으며 항상 성공을 반환 합니다.  호출 사용자 장치를 사용할 수 없게 된 경우 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> WPF의 참조 백 버퍼를 해제 합니다.  장치를 다시 설정 하는 경우 호출 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 에 `backBuffer` 매개 변수를 설정 `null`, 다음 호출 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 을 다시 `backBuffer` 유효한 Direct3D 화면으로 설정.  
  
 다중 어댑터 지원을 구현한 경우에 한해 `Reset` 메서드를 호출하여 유효하지 않은 장치를 복구합니다.  그 이외의 경우에는 모든 Direct3D9 인터페이스를 해제하고 전체적으로 다시 만듭니다.  어댑터 레이아웃이 변경된 경우 변경 전에 만들어진 Direct3D9 개체는 업데이트되지 않습니다.  
  
## 크기 조정 처리  
 경우는 <xref:System.Windows.Interop.D3DImage> 표시 됩니다 기본 크기로 이외의 해상도로에 따라 현재 조절 되지 <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>을 제외 하 고, <xref:System.Windows.Media.Effects.SamplingMode> 에 대 한 대체 <xref:System.Windows.Media.BitmapScalingMode>.  
  
 정확도를 높이려면 <xref:System.Windows.Interop.D3DImage> 컨테이너의 크기가 변경될 때 새 화면을 만들어야 합니다.  
  
 크기 조정은 다음과 같은 세 가지 방법으로 처리할 수 있습니다.  
  
-   크기가 변경되면 레이아웃 시스템에 참여하고 새 화면을 만듭니다.  비디오 메모리가 모두 사용되거나 조각화될 수 있으므로 화면을 너무 많이 만들면 안 됩니다.  
  
-   크기 조정 이벤트가 발생하지 않은 상태로 일정 시간이 경과한 이후에 새 화면을 만듭니다.  
  
-   컨테이너 크기를 1초에 여러 번 확인하는 <xref:System.Windows.Threading.DispatcherTimer>를 만듭니다.  
  
## 다중 모니터 최적화  
 렌더링 시스템에서 <xref:System.Windows.Interop.D3DImage>를 다른 모니터로 이동할 경우 성능이 크게 저하될 수 있습니다.  
  
 WDDM의 경우 각각의 모니터가 동일한 비디오 카드에 연결되어 있고 `Direct3DCreate9Ex`를 사용하면 성능이 저하되지 않습니다.  모니터가 서로 다른 비디오 카드에 연결되어 있으면 성능이 저하됩니다.  Windows XP에서는 성능이 항상 저하됩니다.  
  
 <xref:System.Windows.Interop.D3DImage>가 다른 모니터로 이동하면 해당 어댑터에 새 화면을 만들어 성능을 복구할 수 있습니다.  
  
 성능 저하를 방지하려면 다중 모니터에 맞게 코드를 작성해야 합니다.  다음 목록은 다중 모니터 코드를 작성하는 한 가지 방법을 보여 줍니다.  
  
1.  `Visual.ProjectToScreen` 메서드를 사용하여 화면 공간에서 <xref:System.Windows.Interop.D3DImage>의 점을 찾습니다.  
  
2.  `MonitorFromPoint` GDI 메서드를 사용하여 해당 점을 표시하는 모니터를 찾습니다.  
  
3.  `IDirect3D9::GetAdapterMonitor` 메서드를 사용하여 해당 모니터가 설정된 Direct3D9 어댑터를 찾습니다.  
  
4.  어댑터가 백 버퍼가 있는 어댑터와 다른 경우 새 모니터에 백 버퍼를 새로 만들고 <xref:System.Windows.Interop.D3DImage> 백 버퍼에 할당합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Interop.D3DImage>가 여러 모니터에서 사용되는 경우, WDDM을 사용하도록 구성되고 `IDirect3D9Ex`가 같은 어댑터에 있는 경우가 아니면 성능이 떨어집니다.  이러한 경우에는 성능을 높일 수 있는 방법이 없습니다.  
  
 다음 코드 예제에서는 현재 모니터를 찾는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 <xref:System.Windows.Interop.D3DImage> 컨테이너의 크기나 위치가 변경되면 모니터를 업데이트하거나, 1초당 여러 번 업데이트하는 `DispatcherTimer`를 사용하여 모니터를 업데이트합니다.  
  
## WPF 소프트웨어 렌더링  
 다음과 같은 경우 WPF는 소프트웨어의 UI 스레드에서 동기적으로 렌더링합니다.  
  
-   인쇄  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 이러한 상황이 발생하면 렌더링 시스템은 <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> 메서드를 호출하여 하드웨어 버퍼를 소프트웨어에 복사합니다.  기본 구현을 사용하면 화면과 함께 `GetRenderTargetData` 메서드가 호출됩니다.  이 호출은 Lock\/Unlock 패턴 외부에서 발생하기 때문에 실패할 수 있습니다.  이 경우 `CopyBackBuffer` 메서드가 `null`을 반환하고 이미지가 표시되지 않습니다.  
  
 <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> 메서드를 재정의하고 기본 구현을 호출할 수 있습니다. 이 경우 `null`이 반환되면 자리 표시자 <xref:System.Windows.Media.Imaging.BitmapSource>를 반환할 수 있습니다.  
  
 기본 구현을 호출하는 대신 고유한 소프트웨어 렌더링을 구현할 수도 있습니다.  
  
> [!NOTE]
>  WPF가 소프트웨어에서만 렌더링되면 WPF에 프런트 버퍼가 없기 때문에 <xref:System.Windows.Interop.D3DImage>가 표시되지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Interop.D3DImage>   
 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [연습: WPF에서 Direct3D9 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)