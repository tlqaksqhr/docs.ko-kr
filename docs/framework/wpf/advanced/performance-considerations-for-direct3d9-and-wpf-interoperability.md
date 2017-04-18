---
title: "Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9[WPF 상호 운용성], 성능"
  - "WPF, Direct3D9 상호 운용성 성능"
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항
<xref:System.Windows.Interop.D3DImage> 클래스를 사용하여 Direct3D9 콘텐츠를 호스팅할 수 있습니다.  Direct3D9 콘텐츠를 호스팅하면 응용 프로그램의 성능에 영향을 줄 수 있습니다.  이 항목에서는 WPF\(Windows Presentation Foundation\) 응용 프로그램에서 Direct3D9 콘텐츠를 호스팅할 때 성능을 최적화할 수 있는 유용한 정보를 제공합니다.  여기서 제공되는 유용한 정보에는 <xref:System.Windows.Interop.D3DImage>를 사용하는 방법 및 Windows Vista, Windows XP 및 다중 모니터 디스플레이를 사용할 경우의 유용한 정보가 포함됩니다.  
  
> [!NOTE]
>  이러한 유용한 정보를 보여 주는 코드 예제를 보려면 [WPF 및 Direct3D9 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)를 참조하십시오.  
  
## 필요한 경우에만 D3DImage 사용  
 <xref:System.Windows.Interop.D3DImage> 인스턴스에 호스팅되는 Direct3D9 콘텐츠는 순수 Direct3D 응용 프로그램만큼 빠르게 렌더링되지 않습니다.  화면을 복사하고 명령 버퍼를 플러시하는 작업에는 많은 리소스가 필요할 수 있습니다.  <xref:System.Windows.Interop.D3DImage> 인스턴스 수가 증가하면 플러시도 증가하여 성능이 저하됩니다.  따라서 <xref:System.Windows.Interop.D3DImage>는 꼭 필요한 경우에만 사용하는 것이 좋습니다.  
  
## Windows Vista에 대한 유용한 정보  
 WDDM\(Windows Display Driver Model\)을 사용하도록 구성된 디스플레이를 사용하는 Windows Vista에서 최상의 성능을 얻으려면 Direct3D9 화면을 `IDirect3DDevice9Ex` 장치에 만듭니다.  이렇게 하면 화면을 공유할 수 있습니다.  이 경우 비디오 카드가 Windows Vista에서 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 및 `D3DCAPS2_CANSHARERESOURCE` 드라이버 기능을 지원해야 합니다.  그 외의 다른 설정을 사용하면 소프트웨어를 통해 화면이 복사되어 성능이 크게 저하됩니다.  
  
> [!NOTE]
>  Windows Vista에서 XDDM\(Windows XP Display Driver Model\)을 사용하도록 구성된 디스플레이를 사용하는 경우에는 설정에 관계없이 소프트웨어를 통해 화면이 항상 복사됩니다.  적절한 설정과 비디오 카드를 사용하면 화면 복사가 하드웨어에서 수행되기 때문에 WDDM을 사용할 때 Windows Vista의 성능을 높일 수 있습니다.  
  
## Windows XP에 대한 유용한 정보  
 XDDM\(Windows XP Display Driver Model\)을 사용하는 Windows XP에서 최상의 성능을 얻으려면 `IDirect3DSurface9::GetDC` 메서드가 호출될 때 올바르게 동작하는 잠금 가능한 화면을 만듭니다.  `BitBlt` 메서드는 내부적으로 하드웨어 장치 간에 화면을 전송합니다.  `GetDC` 메서드는 항상 XRGB 화면에서 작동합니다.  그러나 클라이언트 컴퓨터에서 Windows XP SP3 또는 SP2를 실행하며 이 클라이언트에 계층 창 기능을 위한 핫픽스가 적용된 경우 이 메서드는 ARGB 화면에서만 작동합니다.  비디오 카드는 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 드라이브 기능을 지원해야 합니다.  
  
 16비트 바탕 화면 디스플레이를 사용하면 성능이 크게 저하될 수 있으므로  32비트 바탕 화면을 사용하는 것이 좋습니다.  
  
 Windows Vista와 Windows XP용으로 개발하는 경우에는 Windows XP에서 성능을 테스트하십시오.  Windows XP의 경우 비디오 메모리 부족이 문제가 될 수 있습니다.  또한 Windows XP에서는 비디오 메모리 복사 작업을 추가적으로 수행해야 하므로 <xref:System.Windows.Interop.D3DImage>가 Windows Vista WDDM에 비해 비디오 메모리와 대역폭을 많이 사용합니다.  따라서 동일한 비디오 하드웨어를 사용하더라도 Windows Vista보다 Windows XP에서 성능이 떨어집니다.  
  
> [!NOTE]
>  XDDM은 Windows XP와 Windows Vista에서 모두 사용할 수 있지만 WDDM은 Windows Vista에서만 사용할 수 있습니다.  
  
## 일반적인 유용한 정보  
 장치를 만들 때 `D3DCREATE_MULTITHREADED` 생성 플래그를 사용합니다.  이 플래그를 사용하면 성능이 저하되지만 WPF 렌더링 시스템이 다른 스레드에서 이 장치에 대해 메서드를 호출합니다.  한 번에 하나의 스레드만 장치에 액세스하도록 잠금 프로토콜을 올바르게 사용하십시오.  
  
 WPF 관리 스레드에서 렌더링이 수행되는 경우에는 `D3DCREATE_FPU_PRESERVE` 생성 플래그를 사용하여 장치를 만드는 것이 좋습니다.  이 설정을 사용하지 않으면 D3D 렌더링으로 인해 WPF 배정밀도 작업의 정확도가 떨어져 렌더링 문제가 발생할 수 있습니다.  
  
 <xref:System.Windows.Interop.D3DImage>가 포함된 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>를 바둑판식으로 배열하는 경우 또는 하드웨어 지원 없이 비pow2 화면을 바둑판식으로 배열하는 경우가 아니라면 <xref:System.Windows.Interop.D3DImage>를 빠르게 바둑판식으로 배열할 수 있습니다.  
  
## 다중 모니터 디스플레이에 대한 유용한 정보  
 모니터가 여러 대 있는 컴퓨터를 사용하는 경우에는 위에 설명된 유용한 정보를 따르는 것이 좋습니다.  다중 모니터 구성을 사용할 때는 이외에도 몇 가지 성능 고려 사항이 있습니다.  
  
 백 버퍼를 만들면 백 버퍼가 특정 장치 및 어댑터에 만들어지지만 WPF에서는 프런트 버퍼를 임의의 어댑터에 표시할 수 있습니다.  프런트 버퍼를 업데이트하기 위해 어댑터 간에 복사하는 작업에는 리소스가 많이 필요할 수 있습니다.  여러 개의 비디오 카드와 `IDirect3DDevice9Ex` 장치와 함께 WDDM을 사용하도록 구성된 Windows Vista의 경우 동일한 비디오 카드의 다른 어댑터에 프런트 버퍼가 있어도 성능에 아무런 영향이 없습니다.  그러나 Windows XP에서 여러 개의 비디오 카드와 함께 XDDM을 사용할 경우에는 프런트 버퍼가 백 버퍼와 다른 어댑터에 표시되면 성능이 크게 저하될 수 있습니다.  자세한 내용은 [WPF 및 Direct3D9 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)를 참조하십시오.  
  
## 성능 요약  
 다음 표에서는 운영 체제의 기능, 픽셀 형식 및 화면 잠금 가능성에 따른 프런트 버퍼 업데이트의 성능을 보여 줍니다.  여기서는 프런트 버퍼와 백 버퍼가 같은 어댑터에 있다고 가정합니다.  어댑터 구성에 따라 일반적으로 하드웨어 업데이트가 소프트웨어 업데이트보다 훨씬 빠릅니다.  
  
|화면 픽셀 형식|Windows Vista, WDDM 및 9Ex|기타 Windows Vista 구성|Windows XP SP3 또는 SP2\(핫픽스 포함\)|Windows XP SP2|  
|--------------|-------------------------------|-------------------------|-------------------------------------|--------------------|  
|D3DFMT\_X8R8G8B8\(잠글 수 없음\)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT\_X8R8G8B8\(잠글 수 있음\)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|**하드웨어 업데이트**|  
|D3DFMT\_A8R8G8B8\(잠글 수 없음\)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT\_A8R8G8B8\(잠글 수 있음\)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|소프트웨어 업데이트|  
  
## 참고 항목  
 <xref:System.Windows.Interop.D3DImage>   
 [WPF 및 Direct3D9 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)   
 [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [연습: WPF에서 Direct3D9 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)