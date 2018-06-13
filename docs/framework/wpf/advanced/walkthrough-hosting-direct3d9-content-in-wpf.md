---
title: '연습: WPF에서 Direct3D9 콘텐츠 호스팅'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 3b215c0eead8c5fc28b477b81f75c39b5c946302
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546174"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>연습: WPF에서 Direct3D9 콘텐츠 호스팅
이 연습에서는 Windows Presentation Foundation (WPF) 응용 프로그램에서 Direct3D9 콘텐츠를 호스트 하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Direct3D9 콘텐츠를 호스팅하는 WPF 프로젝트를 만듭니다.  
  
-   Direct3D9 콘텐츠를 가져옵니다.  
  
-   Direct3D9 콘텐츠를 사용 하 여 표시 된 <xref:System.Windows.Interop.D3DImage> 클래스입니다.  
  
 작업을 완료 하는 경우에 WPF 응용 프로그램에서 Direct3D9 콘텐츠를 호스트 하는 방법을 알 수 있습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 이상입니다.  
  
-   WPF 호환 형식에서 Direct3D9 콘텐츠를 포함 하는 DLL입니다. 자세한 내용은 참조 [WPF 및 Direct3D9 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) 및 [연습: WPF의 호스팅에 대 한 Direct3D9 콘텐츠 만들기](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)합니다.  
  
## <a name="creating-the-wpf-project"></a>WPF 프로젝트 만들기  
 첫 번째 단계는 WPF 응용 프로그램에 대 한 프로젝트를 만드는 것입니다.  
  
#### <a name="to-create-the-wpf-project"></a>WPF 프로젝트를 만들려면  
  
-   새 WPF 응용 프로그램 프로젝트 만들기 Visual C#에 라는 `D3DHost`합니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.  
  
     MainWindow.xaml 열립니다는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
## <a name="importing-the-direct3d9-content"></a>Direct3D9 콘텐츠 가져오기  
 사용 하 여 관리 되지 않는 DLL에서 Direct3D9 콘텐츠를 가져오면는 `DllImport` 특성입니다.  
  
#### <a name="to-import-direct3d9-content"></a>Direct3D9 콘텐츠를 가져오려면  
  
1.  MainWindow.xaml.cs를 코드 편집기에서 엽니다.  
  
2.  자동으로 생성 된 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Direct3D9 콘텐츠 호스팅  
 마지막으로 사용 하 여는 <xref:System.Windows.Interop.D3DImage> Direct3D9 콘텐츠를 호스트 하는 클래스입니다.  
  
#### <a name="to-host-the-direct3d9-content"></a>Direct3D9 콘텐츠를 호스트 하려면  
  
1.  MainWindow.xaml에서 자동으로 생성 된 XAML을 다음 XAML로 바꿉니다.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  프로젝트를 빌드합니다.  
  
3.  Direct3D9 콘텐츠 bin/Debug 폴더를 포함 하는 DLL을 복사 합니다.  
  
4.  F5 키를 눌러 프로젝트를 실행합니다.  
  
     WPF 응용 프로그램 내에서 Direct3D9 내용이 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.D3DImage>  
 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
