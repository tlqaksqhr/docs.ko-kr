---
title: Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 52085579c2a432e7db1ebec096a931e0d51718f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항
사용 하 여 Direct3D9 콘텐츠를 호스팅할 수는 <xref:System.Windows.Interop.D3DImage> 클래스입니다. Direct3D9 콘텐츠를 호스트 응용 프로그램의 성능 영향을 줄 수 있습니다. 이 항목에서는 Windows Presentation Foundation (WPF) 응용 프로그램에서 Direct3D9 콘텐츠를 호스트 하는 경우 성능을 최적화 하는 모범 사례를 설명 합니다. 이러한 최선의 방법을 사용 하는 방법이 <xref:System.Windows.Interop.D3DImage> 다중 모니터를 표시 하 고 Windows Vista, Windows XP를 사용 하는 모범 사례 및 합니다.  
  
> [!NOTE]
>  이들 모범 사례를 보여 주는 코드 예제를 보려면 [WPF 및 Direct3D9 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)합니다.  
  
## <a name="use-d3dimage-sparingly"></a>D3DImage를 제한적으로 사용  
 Direct3D9 콘텐츠에서 호스팅되는 <xref:System.Windows.Interop.D3DImage> 인스턴스는 순수 Direct3D 응용 프로그램용 빠르지로 렌더링 하지 않습니다. 화면을 복사 하 고 명령 버퍼를 플러시하여 비용이 많이 드는 작업 될 수 있습니다. 개수로 <xref:System.Windows.Interop.D3DImage> 인스턴스 증가 하는 경우 더 많은 플러시 작업이 발생 하지 않으며 성능이 저하 됩니다. 따라서 사용 해야 <xref:System.Windows.Interop.D3DImage> 제한적으로 사용 합니다.  
  
## <a name="best-practices-on-windows-vista"></a>Windows Vista에서 모범 사례  
 최상의 성능을 위해서는 Windows Vista에서 Windows 표시 드라이버 모델 (WDDM)를 사용 하도록 구성 된 디스플레이 사용 하면 Direct3D9 노출에 만들는 `IDirect3DDevice9Ex` 장치입니다. 이 화면의 공유를 사용할 수 있습니다. 비디오 카드를 지원 해야 합니다는 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 및 `D3DCAPS2_CANSHARERESOURCE` Windows vista 드라이버 기능입니다. 다른 모든 설정을 화면이 소프트웨어 성능이 크게 저하를 통해 복사 되어 발생 합니다.  
  
> [!NOTE]
>  Windows Vista에서 Windows XP 표시 드라이버 모델 (XDDM)를 사용 하도록 구성 되어 있는 디스플레이, 표면은 항상 설정에 관계 없이 소프트웨어를 통해 복사 됩니다. 적절 한 설정 및 비디오 카드를 사용 하 여 하드웨어에서 화면 복사가 수행 되기 때문에 WDDM를 사용 하는 경우 Windows Vista 더 나은 성능을 표시 됩니다.  
  
## <a name="best-practices-on-windows-xp"></a>Windows XP에서 모범 사례  
 Windows XP 디스플레이 드라이버 모델 (XDDM)를 사용 하는 Windows XP에서 최상의 성능을 위해가 올바르게 작동 하는 잠글 수 있는 화면을 만들 때는 `IDirect3DSurface9::GetDC` 메서드를 호출 합니다. 내부적으로 `BitBlt` 메서드 하드웨어의 장치에서 화면을 전송 합니다. `GetDC` xrgb 화면에서 항상 사용할 수 있는 방법입니다. 그러나 클라이언트 컴퓨터가 SP3 또는 SP2, Windows XP를 실행 및 클라이언트에 계층화 된 창의 기능에 대 한 핫픽스 하는 경우이 방법을 사용 ARGB 화면 합니다. 비디오 카드를 지원 해야 합니다는 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 드라이버 기능입니다.  
  
 16 비트 바탕 화면 깊이 성능이 크게 저하 수 있습니다. 32 비트 데스크톱을 사용 하는 것이 좋습니다.  
  
 Windows Vista 및 Windows XP 개발 하는 경우에 Windows XP에서 성능을 테스트 합니다. Windows XP에서 비디오 메모리가 부족 하 여 실행은 문제가. 또한 <xref:System.Windows.Interop.D3DImage> Windows XP에서 더 많은 비디오 메모리와 필요한 추가 비디오 메모리 복사본으로 인해 Windows Vista WDDM 보다 대역폭을 사용 하 여 합니다. 따라서 성능이 비디오는 동일한 하드웨어에 대 한 보다 Windows Vista에서 Windows XP에서 뒤 처 집니다 기대할 수 있습니다.  
  
> [!NOTE]
>  XDDM는 Windows XP 및 Windows Vista; 모두에서 사용할 수 그러나 WDDM은 Windows Vista에만 사용할 수 있습니다.  
  
## <a name="general-best-practices"></a>유용한 일반 정보  
 장치를 만들 때 사용 된 `D3DCREATE_MULTITHREADED` 생성 플래그입니다. 성능, 줄어들지만 WPF 렌더링 시스템이이 장치에 다른 스레드에서 메서드를 호출 합니다. 사용할 두 개의 스레드가 동시에 액세스할 수 있도록 잠금 프로토콜을 올바르게 수행 해야 합니다.  
  
 렌더링을 관리 되는 WPF 스레드에서 수행이 가장 좋습니다 사용 하 여 장치를 만드는 `D3DCREATE_FPU_PRESERVE` 생성 플래그입니다. 이 설정이 없으면 D3D 렌더링 WPF 배정도 작업의 정확도 하 고 렌더링 문제가 발생할 수 있습니다.  
  
 바둑판식으로 배열는 <xref:System.Windows.Interop.D3DImage> 경우 또는 하드웨어 지원 사용 하지 않는 비 pow2 화면 타일 하지 않는 한도 빠르지만 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush> 를 포함 하는 <xref:System.Windows.Interop.D3DImage>합니다.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>다중 모니터 디스플레이 대 한 모범 사례  
 모니터가 여러 개 있는 컴퓨터를 사용 하는 경우 앞에서 설명한 모범 사례를 따라야 합니다. 다중 모니터 구성에 대 한 몇 가지 추가적인 성능 고려 사항이 있습니다.  
  
 백 버퍼를 만들 때 특정 장치 및 어댑터에 생성 됩니다. 하지만 WPF 모든 어댑터에 프런트 버퍼를 표시할 수 있습니다. 전면 버퍼를 업데이트 하기 위해 어댑터 간에 복사 하는 것은 비용이 매우 많이 들 수 있습니다. WDDM 여러 개의 비디오 카드를 사용 하 여 사용 하도록 구성 된 Windows Vista에서는 `IDirect3DDevice9Ex` 장치 프런트 버퍼 다른 어댑터 하지만 여전히 동일한 비디오 카드에 있으면 없습니다 성능 저하 됩니다. 그러나, Windows XP 및 XDDM 비디오 카드가 여러 개 있는 경우에 성능이 크게 저하 프런트 버퍼 백 버퍼 다른 어댑터에 표시 될 때. 자세한 내용은 참조 [WPF 및 Direct3D9 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)합니다.  
  
## <a name="performance-summary"></a>성능 요약  
 다음 표에서 운영 체제, 픽셀 형식 및 화면 잠금 가능성의 함수로 프런트 버퍼 업데이트의 성능을 보여 줍니다. 전면 버퍼 및 백 버퍼 동일한 어댑터에 있는 것으로 간주 됩니다. 어댑터 구성에 따라 하드웨어 업데이트를 일반적으로 소프트웨어 업데이트 보다 훨씬 빠릅니다.  
  
|화면 픽셀 형식|Windows Vista, WDDM 및 9Ex|다른 Windows Vista 구성|Windows XP SP3 또는 핫픽스 w / s p 2|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (잠글 수 없습니다)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT_X8R8G8B8 (잠금 가능)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|**하드웨어 업데이트**|  
|D3DFMT_A8R8G8B8 (잠글 수 없습니다)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT_A8R8G8B8 (잠금 가능)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|소프트웨어 업데이트|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.D3DImage>  
 [WPF 및 Direct3D9 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
 [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [연습: WPF에서 Direct3D9 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
